---
title: 'Учебный пример: масштабирование Datascape на устройствах, которые имеют различный уровень производительности'
description: В этом практическом представлены подробные сведения о как разработчики Microsoft оптимизировать приложение Datascape для разработки удобную среду для устройств с помощью широкий набор возможностей производительности.
author: danandersson
ms.author: alexturn
ms.date: 03/21/2018
ms.topic: article
keywords: насыщенные гарнитуры, пример виртуальной Реальности, для оптимизации производительности
ms.openlocfilehash: 990a5ee6de07b6416e3150a7885220409a9c8d93
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59604873"
---
# <a name="case-study---scaling-datascape-across-devices-with-different-performance"></a>Учебный пример: масштабирование Datascape на устройствах, которые имеют различный уровень производительности

Datascape представляет собой приложение Windows Mixed Reality, внутренней разработки в корпорации Майкрософт где мы ознакомились с отображением данных о погоде на основе данных ландшафта. Приложение описывается уникальных ценных сведений, которые пользователи получают из обнаружение данных в смешанной реальности, заключив пользователя с помощью визуализации данных holographic.

Для Datascape мы хотели предназначены для различных платформ с различных аппаратных возможностей, начиная от Microsoft HoloLens в Windows Mixed Reality иммерсивную и от малой ПК до самой последней ПК с высоким быстродействием GPU. Основная проблема была Подготовка к просмотру наших сцены в визуально привлекательные вопрос на устройствах с совершенно другое графические возможности во время выполнения при высокой частоте кадров.

В этом практическом проведет через процесс и методики, используемые для создания, некоторые из наших дополнительные систем интенсивно использующих графический Процессор с описанием проблемы, с которыми мы столкнулись, и как мы позволяют обойти их.

## <a name="transparency-and-overdraw"></a>Прозрачность и может быть нарисован поверх

Наши основные отрисовки трудностей обработаны прозрачности, поскольку прозрачности, могут потреблять на графическом Процессоре.

Сплошная линия геометрического объекта может визуализироваться сверху вниз при записи в буфер глубины, остановка любой будущих пикселей, расположенных за точки из уничтожается. Это предотвращает выполнение построителя текстуры, значительно ускоряет процесс скрытые пикселей. Если geometry оптимально отсортировано, каждый пиксель на экране будет отображен только один раз.

Прозрачный geometry сортироваться обратно на передний план и зависит от того, наложения выходные данные шейдера пикселей для текущего пикселя на экране. Это может привести каждого пикселя на экране, отрисовывается в несколько раз на кадр, называются перерисовывать.

Для HoloLens и массовым ПК, экрана может быть заполнен только небольшое число раз, прозрачность, Подготовка к просмотру проблематичным.

## <a name="introduction-to-datascape-scene-components"></a>Введение в компоненты Datascape сцены

Нам необходимо было три основных компонента наших сцены; **пользовательского интерфейса, карты**, и **погоды**. На раннем этапе мы знали, что наши эффекты погоды потребует время GPU, он может получить, поэтому мы разработали специально пользовательского интерфейса и ландшафта, способом, который сведет любой перекрытий.

Мы переработали пользовательский Интерфейс несколько раз свести к минимуму объем перерисовывать он создается. Мы сделали ошибку боковой части более сложной геометрии, а не прозрачного art наложение друг над другом для компонентов, таких как свечение обзоры кнопки и карты.

Карты мы использовали пользовательский шейдер, который бы убрать стандартные возможности Unity, такие как сложные освещения и появлении теней их замены с моделью освещения простой единый sun и вычисление пользовательских туман. Это созданный простой построитель текстуры и освободите циклов GPU.

Нам удалось получить пользовательский Интерфейс и карту для подготовки к просмотру в бюджет где нам не нужно любые изменения их в зависимости от оборудования; Тем не менее погоды визуализации, в частности облачная отрисовка, оказалось действительно сложная!

## <a name="background-on-cloud-data"></a>Сведения о данных в облаке

Наших облачных данных был загружен с серверов NOAA (http://nomads.ncep.noaa.gov/) и перешла к нам в три различных 2D слоев, каждый из которых высоту верхней и нижней частях облака, а также плотность облака для каждой ячейки сетки. В текстуры info cloud хранения каждого компонента в компоненте красного, зеленого и синего текстуры для быстрого доступа в GPU, получили обрабатывать данные.

## <a name="geometry-clouds"></a>Geometry облака

Чтобы убедиться в том, что наши компьютеры малой могут сделать наши облака, которые мы решили начать с перерисовывать подход, который лучше использовать сплошной свести к минимуму.

Во-первых, мы попытались создания облаков, создавая карты высоты сплошная сетки для каждого слоя, создание фигуры с помощью radius текстуры info cloud на вершину. Шейдер геометрии мы использовали для создания вершины в верхней и нижней частью облака, создание сплошной cloud фигур. Мы использовали значение плотности из текстуры для цвета в облако с более темные цвета для более плотных облаков.

**Шейдер по созданию вершин:**

```
v2g vert (appdata v)
{
    v2g o;
    o.height = tex2Dlod(_MainTex, float4(v.uv, 0, 0)).x;
    o.vertex = v.vertex;
    return o;
}
 
g2f GetOutput(v2g input, float heightDirection)
{
    g2f ret;
    float4 newBaseVert = input.vertex;
    newBaseVert.y += input.height * heightDirection * _HeigthScale;
    ret.vertex = UnityObjectToClipPos(newBaseVert);
    ret.height = input.height;
    return ret;
}
 
[maxvertexcount(6)]
void geo(triangle v2g p[3], inout TriangleStream<g2f> triStream)
{
    float heightTotal = p[0].height + p[1].height + p[2].height;
    if (heightTotal > 0)
    {
        triStream.Append(GetOutput(p[0], 1));
        triStream.Append(GetOutput(p[1], 1));
        triStream.Append(GetOutput(p[2], 1));
 
        triStream.RestartStrip();
 
        triStream.Append(GetOutput(p[2], -1));
        triStream.Append(GetOutput(p[1], -1));
        triStream.Append(GetOutput(p[0], -1));
    }
}
fixed4 frag (g2f i) : SV_Target
{
    clip(i.height - 0.1f);
 
    float3 finalColor = lerp(_LowColor, _HighColor, i.height);
    return float4(finalColor, 1);
}
```

Мы представили небольшой шум, чтобы получить более подробные сведения на основе реальных данных. Для создания краев round облака, мы обрезается пиксели в шейдер пикселей, помеченным radius интерполированное значение пороговое значение, чтобы отменить практически без значений.

![Geometry облака](images/datascape-geometry-clouds-700px.jpg)

Так как облака geometry сплошная линия, они могут быть представлены перед ландшафта, чтобы скрыть точки дорогостоящие карты под для дальнейшего повышения частоты кадров. Это решение выполнялись на всех графических плат из спецификации min видеокарт, а также на HoloLens, из-за подход отрисовки geometry сплошная линия.

## <a name="solid-particle-clouds"></a>Сплошной частиц облака

Теперь у нас было резервного копирования, который неплохую представлением наших облачных данных, но был немного lackluster фактора «Да» и был передает объемные считают, что нам требовалось для наших высокопроизводительных машинах.

Следующим этапом создании облака, представляя их с 100 000 примитивы, для создания более естественному и объемные вид.

Сортировать от передних к задним частицы оставаться сплошной, мы может принести пользу глубина буфера, визуализируемых пикселей за ранее готовый для просмотра частицы уменьшение перекрытий. Кроме того с помощью решения на основе частиц, мы можем изменить объем примитивы, используемые на другое оборудование целевого. Тем не менее все пиксели по-прежнему должны быть протестированы глубины, что приведет к появлению некоторыми дополнительными издержками.

Во-первых мы создали частиц позиций относительно центральной точки работы во время запуска. Мы распределенных частицы более плотно вокруг центра и менее сложным в расстояние. Таким образом, чтобы сначала визуализируются ближайший частицы мы предварительно отсортированы все примитивы в центре на задний план.

Вычислительного шейдера бы образец текстуры info облако для размещения каждой частиц в правильный высоту и цвет, который оно зависит от плотности.

Мы использовали *DrawProcedural* для подготовки к просмотру квадрант на примитив, позволяя частиц данные оставались на GPU, все время.

Каждую частицу содержится высоту и radius. Высота был основан на облачные данные, взятых из текстуры info облака и радиус был основан на первоначального распространения, где он будет вычисляться для хранения расстояние по горизонтали для ближайшего соседа. Четырехугольники будет использовать эти данные, чтобы сориентировать себя под углом по высоте, когда пользователи рассматривать по горизонтали, появлялась высота, и когда пользователи рассмотрели его сверху вниз, будет рассматриваться область между своим соседям.

![Примитив фигуры](images/particle-shape-700px.png)

**Код шейдера, показывающий распределение:**

```
ComputeBuffer cloudPointBuffer = new ComputeBuffer(6, quadPointsStride);
cloudPointBuffer.SetData(new[]
{
    new Vector2(-.5f, .5f),
    new Vector2(.5f, .5f),
    new Vector2(.5f, -.5f),
    new Vector2(.5f, -.5f),
    new Vector2(-.5f, -.5f),
    new Vector2(-.5f, .5f)
});
 
StructuredBuffer<float2> quadPoints;
StructuredBuffer<float3> particlePositions;
v2f vert(uint id : SV_VertexID, uint inst : SV_InstanceID)
{
    // Find the center of the quad, from local to world space
    float4 centerPoint = mul(unity_ObjectToWorld, float4(particlePositions[inst], 1));
 
    // Calculate y offset for each quad point
    float3 cameraForward = normalize(centerPoint - _WorldSpaceCameraPos);
    float y = dot(quadPoints[id].xy, cameraForward.xz);
 
    // Read out the particle data
    float radius = ...;
    float height = ...;
 
    // Set the position of the vert
    float4 finalPos = centerPoint + float4(quadPoints[id].x, y * height, quadPoints[id].y, 0) * radius;
    o.pos = mul(UNITY_MATRIX_VP, float4(finalPos.xyz, 1));
    o.uv = quadPoints[id].xy + 0.5;
 
    return o;
}
```

Так как мы сортировки частицы начала к концу, и мы по-прежнему использовать сплошной стиль шейдера пикселей прозрачный клипов (не blend), этот метод обрабатывает возрасти примитивы, как избежать дорогостоящей чрезмерное draw даже на компьютерах, маломощное.

## <a name="transparent-particle-clouds"></a>Прозрачный частиц облака

Сплошной частицы приведен органических понимание к фигуре облаков, но по-прежнему требуется что-то продать fluffiness облаков. Мы решили попробовать пользовательское решение для видеокарт, где мы можем быстрее выводить прозрачности.

Для этого мы просто переключить исходный порядок сортировки частицы и изменить шейдер, который нужно использовать альфа-канал текстуры.

![Компания облака](images/fluffy-clouds-700px.jpg)

Он отлично выглядели но оказался слишком большими для даже самые сложные компьютеров, так как это приведет к визуализации каждого пикселя на экране сотни раз!

## <a name="render-off-screen-with-lower-resolution"></a>Визуализации вне экрана с низким разрешением

Чтобы уменьшить количество пикселей, преобразовываемый для облака, мы начали, обработав их в буфере квартала разрешения (по сравнению с экрана) и растяжение в результате резервного копирования на экран после рисования всех частей. Это дает примерно 4 x ускорение, но прилагается несколько предостережений.

**Код для подготовки к просмотру вне экрана:**

```
cloudBlendingCommand = new CommandBuffer();
Camera.main.AddCommandBuffer(whenToComposite, cloudBlendingCommand);
 
cloudCamera.CopyFrom(Camera.main);
cloudCamera.rect = new Rect(0, 0, 1, 1);    //Adaptive rendering can set the main camera to a smaller rect
cloudCamera.clearFlags = CameraClearFlags.Color;
cloudCamera.backgroundColor = new Color(0, 0, 0, 1);
 
currentCloudTexture = RenderTexture.GetTemporary(Camera.main.pixelWidth / 2, Camera.main.pixelHeight / 2, 0);
cloudCamera.targetTexture = currentCloudTexture;
 
// Render clouds to the offscreen buffer
cloudCamera.Render();
cloudCamera.targetTexture = null;
 
// Blend low-res clouds to the main target
cloudBlendingCommand.Blit(currentCloudTexture, new RenderTargetIdentifier(BuiltinRenderTextureType.CurrentActive), blitMaterial);
```

Во-первых при подготовке к просмотру в во буфере вне экрана, вдруг всех сведениях из наших основных сцены, в результате чего частицы за горы подготовки к просмотру на основе mountain.

Во-вторых также растягивания буфера появился артефактов на краях наших облаков, где был заметно изменяет разрешение. Следующих двух разделах поговорим о том, как мы устранения этих проблем.

## <a name="particle-depth-buffer"></a>Буфер глубины частиц

Чтобы сделать частицы совместно работать с трехмерной геометрии, где mountain или объект стоит осветить частицы за ней, заполненное буфере вне экрана с буфер глубины, содержащий геометрии сцены основной. Для создания такого буфера глубины, мы создали второй камеры, Подготовка к просмотру только сплошная геометрии и глубина сцены.

Затем мы использовали создать текстуру в шейдер пикселей облаков для скрывать пикселей. Мы использовали той же текстуры для вычисления расстояния к данной геометрии за точки облака. Используя расстояние между ними и применять его в качестве альфа пикселя, у нас теперь было эффект облаков исчезновение, как можно ближе к ландшафта, удаление любого жесткого порезов, когда удовлетворяют примитивов и ландшафта.

![Смешением в ландшафта облака](images/clouds-blended-to-terrain-700px.jpg)

## <a name="sharpening-the-edges"></a>Увеличение резкости краев

Облака растягивается вверх выглядело почти идентичен нормального размера облака в центре частицы или там, где они overlapped, но показал некоторые артефакты на краях облака. В противном случае четкие границы выглядит нечетким и эффекты псевдоним были введены при перемещении камеры.

Мы решили эту проблему, выполнив простой шейдер в буфере вне экрана, чтобы определить, где много важных изменений в отличие от этого (1). Мы опубликовали пиксели с большими изменениями в новый буфер шаблона (2). Затем мы использовали буфер шаблона маске этих областей Высокая контрастность при применении буфере вне экрана, на экран, приводит к уязвимости в и вокруг облака (3).

Мы затем подготавливается к просмотру всех частей снова в полноэкранном режиме, но сейчас используется буфер шаблона, чтобы маскировать все, но края, приводит к минимальный набор пикселей пользовался (4). Поскольку буфер команд уже был создан для частицы, нам просто пришлось визуализировать его снова в новую камеру.

![Ход отрисовки границ облака](images/cloud-steps-1-4-700px.jpg)

В результате был четкие границы с разделами требует больших затрат центра облаков.

Хотя это было намного быстрее, чем подготовки к просмотру все примитивы в полноэкранный режим, по-прежнему затраты, связанные с тестированием пикселей от буфер шаблона, чтобы по-прежнему перерисовывать большие объемы прилагается затраты.

## <a name="culling-particles"></a>Исключения примитивов

Для наших эффекта ветра созданного нами долго лент треугольника в вычислительном шейдере, создание многие поставщики из ветра в мире. Эффект ветра была не создает большой нагрузки на коэффициент заполнения, из-за тонким полосы создан, но он преобразовывался многие сотни тысяч вершины, что в результате в условиях большой нагрузки для шейдера вершин.

Мы представили append буферы на вычислительного шейдера для веб-канала подмножество ветра полосковых линий для отрисовки. Простое представление пирамиды обзора установлена логики в вычислительного шейдера мы могли бы определить, было ли полоса за пределами представления камеры и предотвратить добавление буфер Push-уведомлений. Это количество лент значительно сократить, освободить некоторые необходимые циклов в GPU.

**Кода, демонстрирующий используется буфер append:**

*Вычислить шейдер:*

```
AppendStructuredBuffer<int> culledParticleIdx;
 
if (show)
    culledParticleIdx.Append(id.x);
```

*C#код:*

```
protected void Awake() 
{
    // Create an append buffer, setting the maximum size and the contents stride length
    culledParticlesIdxBuffer = new ComputeBuffer(ParticleCount, sizeof(int), ComputeBufferType.Append);
 
    // Set up Args Buffer for Draw Procedural Indirect
    argsBuffer = new ComputeBuffer(4, sizeof(int), ComputeBufferType.IndirectArguments);
    argsBuffer.SetData(new int[] { DataVertCount, 0, 0, 0 });
}
 
protected void Update()
{
    // Reset the append buffer, and dispatch the compute shader normally
    culledParticlesIdxBuffer.SetCounterValue(0);
 
    computer.Dispatch(...)
 
    // Copy the append buffer count into the args buffer used by the Draw Procedural Indirect call
    ComputeBuffer.CopyCount(culledParticlesIdxBuffer, argsBuffer, dstOffset: 1);
    ribbonRenderCommand.DrawProceduralIndirect(Matrix4x4.identity, renderMaterial, 0, MeshTopology.Triangles, dataBuffer);
}
```

Мы пробовали, используя ту же методику на частицы облака, где мы исключать их на вычислительного шейдера и только передача видимым частицы к просмотру. Этот метод фактически не сохраняли нам большую в GPU момента пиксели сумма отображается на экране и не включает стоимость вычисления вершины крупнейших узким местом.

Другая проблема с помощью этого способа был, что добавление буфер заполнен в случайном порядке из-за своей природе распараллеленного частицы, вызывая отсортированный частицы быть без отсортированными, приводит к мелькания частицы облачных вычислений.

Существуют способы сортировки буфере Push-уведомлений, но ограниченный объем рост производительности, который мы получили из визуализируемых частицы бы смещение с дополнительную сортировку, скорее всего, мы решили не реализации этой оптимизации.

## <a name="adaptive-rendering"></a>Адаптивная отрисовка

Для обеспечения постоянной частоты кадров на приложения с различными Подготовка к просмотру условия, такие как облачно vs в четкое мы представили адаптивной отрисовки на уровне приложения.

Адаптивная отрисовка первым делом для измерения GPU. Мы сделали это, вставив пользовательский код в буфер команд GPU в начале и конце Отрисованный кадр, обе записи слева и справа глаз времени экрана.

Измеряя время, затраченное визуализации и ее сравнение с нашей требуемой-частота обновления Наша текущая понять, насколько близко, нам пришлось пропуск кадров.

Если рядом с удалением кадров, мы адаптировать наших отрисовки для ускорения. Один из простых способов адаптации изменяют размер окна просмотра экрана, требуя визуализирован меньше точек.

С помощью *UnityEngine.XR.XRSettings.renderViewportScale* система сжимает целевого окна просмотра и автоматически растягивает результат резервного копирования по размеру экрана. Небольшое изменение в шкале выходит на трехмерной геометрии и масштабный коэффициент 0,7 требует половина объема пикселей для отображения.

![Масштаб 70%, половина пикселей](images/datascape-scaling-700px.jpg)

При обнаружении, то, что не будет удалено кадров нам уменьшить масштаб с фиксированным числом и повысить его обратно, когда мы запускаем достаточно быстро еще раз.

Хотя мы решили, какой способ облака для использования на основе графических возможностей оборудования во время запуска, возможно, основываться на данных из измерения GPU, чтобы запретить системе staying с низким разрешением, в течение длительного времени, но это что-то мы не было времени  Чтобы изучить данные в Datascape.

## <a name="final-thoughts"></a>Заключительные замечания

Предназначенные для различных аппаратных средств является довольно сложной и требует определенного планирования.

Мы рекомендуем начать предназначенных для малой машин, чтобы ознакомиться с пространство проблемы и разрабатывать решения архивации, которое будет выполняться на всех компьютерах. При разработке решения с коэффициент заполнения в виду, так как будут самый ценный ресурс. Целевой объект geometry сплошная линия по прозрачности.

С решением архивации можно запустите слоев в дополнительные сложности для машин верхний предел или может быть просто повысить разрешения из решения для архивации.

Проектирование для худшего варианта развития и может быть рассмотрите возможность использования адаптивной отрисовки для случаев большой.

## <a name="about-the-authors"></a>Об авторах

<table style="border:0">
<tr>
<td style="border:0" width="60px"><img alt="Picture of Robert Ferrese" width="60" height="60" src="images/robert-ferrese-60px.jpg"></td>
<td style="border:0"><b>Роберт Ferrese</b><br>Разработчик программного обеспечения @Microsoft</td>
</tr>
<tr>
<td style="border:0" width="60px"><img alt="Picture of Dan Andersson" width="60" height="60" src="images/dan-andersson-60px.jpg"></td>
<td style="border:0"><b>Дэн Andersson</b><br>Разработчик программного обеспечения @Microsoft</td>
</tr>
</table>


## <a name="see-also"></a>См. также
* [Основные сведения о производительности для смешанной реальности](understanding-performance-for-mixed-reality.md)
* [Рекомендации по производительности для Unity](performance-recommendations-for-unity.md)

 