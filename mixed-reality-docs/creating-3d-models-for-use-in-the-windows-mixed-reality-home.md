---
title: Создавать трехмерные модели для использования в домашних
description: Требования к активов и разработка рекомендации для трехмерных моделей для использования в Windows Mixed Reality на HoloLens и иммерсивную (VR).
author: thmignon
ms.author: thmignon
ms.date: 03/21/2018
ms.topic: article
keywords: Ограничивает 3D, для моделирования, руководство, требования к активов, разработки, рекомендации, средства запуска, 3D запуска, текстуры, материалов, сложности, треугольники, сетки, многоугольники, polycount,
ms.openlocfilehash: 73af40cf2915742cab612625c8243a36ee74d748
ms.sourcegitcommit: f20beea6a539d04e1d1fc98116f7601137eebebe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66692284"
---
# <a name="create-3d-models-for-use-in-the-home"></a>Создавать трехмерные модели для использования в домашних

[Windows Mixed Reality домашней](navigating-the-windows-mixed-reality-home.md) является отправной точкой, где пользователи будут располагаться перед запуском приложения. Можно разработать приложение для гарнитуры смешанной реальности Windows использовать [трехмерной модели в качестве средства запуска приложений](implementing-3d-app-launchers.md) и позволить [3D прямые ссылки должен быть помещен в Windows Mixed Reality домашней](implementing-3d-app-launchers.md#3d-deep-links-secondarytiles) из в приложении. В этой статье приведены рекомендации по созданию совместимы с Windows Mixed Reality домашней трехмерных моделей.

## <a name="asset-requirements-overview"></a>Обзор требований активов
При создании трехмерных моделей для смешанной реальности Windows имеются некоторые требования, которым должны соответствовать все ресурсы: 
1. [Экспорт](#exporting-models) -активы должны доставляться в формат файла .glb (двоичный glTF)
2. [Моделирование](#modeling-guidelines) -активы должна быть менее 10 k треугольники, иметь не более 64 узлов и 32 submeshes на текстур и
3. [Материалы](#material-guidelines) - текстуры не может превышать 4096 x 4096 и наименьшее mip-карты должен быть не больше 4 в любом измерении
4. [Анимация](#animation-guidelines) -анимации не может быть длиннее 20 минут, 30 кадров в секунду (36,000 опорные кадры) и должен содержать < = 8192 morph целевой вершины
5. [Оптимизация](#optimizations) -активы должны быть оптимизированы с помощью [WindowsMRAssetConverter](https://github.com/Microsoft/glTF-Toolkit/releases). Это **на версиях ОС Windows требуется < = 1709** и рекомендуется использовать на версиях ОС Windows > = 1803

В оставшейся части этой статьи включает подробный обзор этих требований а также дополнительные правила чтобы убедиться, что моделей для работы с Windows Mixed Reality home. 

## <a name="detailed-guidance"></a>Подробные инструкции

### <a name="exporting-models"></a>Экспорт моделей

Windows Mixed Reality домашней ожидает трехмерных ресурсов, доставляемой с помощью формата файла .glb с внедренные изображения и двоичные данные. Командной является двоичную версию glTF формате, который платными свободного открытый стандарт для доставки трехмерных активов, обслуживается Khronos группы. По мере развития glTF как отраслевой стандарт для 3D-содержимого с возможностью взаимодействия в приложениях Windows и интерфейсы дадут корпорации Майкрософт поддержка формата. Если вы еще не создали ресурс glTF, прежде чем вы найдете [список поддерживаемых экспорта и преобразователями](https://github.com/KhronosGroup/glTF/blob/master/README.md#converters-and-exporters) на странице github glTF рабочей группы.  

### <a name="modeling-guidelines"></a>Рекомендации по моделированию

Windows ожидает, что ресурсы, чтобы быть созданы с помощью следующих правил моделирования для обеспечения совместимости с домов смешанной реальности. При моделировании в программе по своему усмотрению учитывайте следующие рекомендации и ограничения:
1. Доступ к оси должно быть присвоено значение «Y».
2. Ресурс должен сталкиваются «forward» к положительным оси Z.
3. Все ресурсы, которые должен быть построен на плоскости нуля в начале координат сцены (0,0,0)
4. Работа единицы должно быть присвоено счетчики и средства, чтобы ресурсы могут быть созданы в масштабе по всему миру
5. Все сетки не обязательно должны быть объединены, но рекомендуется, если вы используете устройств с ограниченными ресурсами
6. Все слои взаимодействия между должно использовать 1 материал с только 1 текстуры, набор, используемый для всего активов
7. UVs должны быть упорядочены в порядке square в 0-1 места. Избегайте заполнения текстуры, несмотря на то, что они разрешены.
8. С несколькими UVs не поддерживаются.
9. Двойные односторонний материалы не поддерживаются.

### <a name="triangle-counts-and-levels-of-detail-lods"></a>Счетчики треугольник и уровни детализации (LODs)

Windows Mixed Reality домашней не поддерживает модели с более чем 10 000 треугольники. Рекомендуется выполнить триангуляцию вашей сеток перед экспортом, чтобы убедиться, что они не превышает это число. Windows MR также поддерживает необязательные geometry уровни детализации (LODs) для обеспечения производительности и качества высокого качества. [WindowsMRAssetConverter](https://github.com/Microsoft/glTF-Toolkit/releases) можно объединить в единый .glb модель 3 версии модели. Windows определяет, какие текстур и для отображения на основе суммы реальный объем экрана, занимаемого моделью. Только три уровня текстур и поддерживаются следующие рекомендуемые счетчики треугольник:
<br>

|  Уровень текстур и  |  Рекомендуемое число треугольник  |  Максимальное число треугольник | 
|------|------|------|
|  ТЕКСТУР И 0 |  10,000 |  10,000 | 
|  ТЕКСТУР И 1 |  5,000  |  10,000 | 
|  ТЕКСТУР И 2 |  2,500  |  10,000 | 

### <a name="node-counts-and-submesh-limits"></a>Счетчики узла и ограничения вложенной сетки
Windows Mixed Reality домашней не поддерживает модели с более чем 64 узлов или 32 submeshes на текстур и. Узлы являются понятием в [glTF спецификации](https://github.com/KhronosGroup/glTF/tree/master/specification/2.0#nodes-and-hierarchy) , которые определяют объекты в сцене. Submeshes определены в массиве [примитивы](https://github.com/KhronosGroup/glTF/tree/master/specification/2.0#meshes) в сетке в объекте. 

|  Компонент |  Описание  |  Max поддерживается | Документация |
|------|------|------|------|
|  Узлы |  Объекты в glTF сцены |  64 для текстур и | [Здесь](https://github.com/KhronosGroup/glTF/tree/master/specification/2.0#nodes-and-hierarchy)|
|  Submeshes |  Сумма примитивы на все сетки |  32 на текстур и | [Здесь](https://github.com/KhronosGroup/glTF/tree/master/specification/2.0#meshes)|

## <a name="material-guidelines"></a>Рекомендации по материала

С помощью рабочего состояния системы неровности PBR следует быть готовым текстуры. Начните с создания полный набор текстур, включая Albedo, обычный, перекрытия, «металлик,» и неровности. Windows Mixed Reality поддерживает текстуры с разрешением вверх до 4096 x 4096, но его рекомендуется автором в по 512 x 512. Кроме того текстуры должны разрабатываться с разрешением, кратное 4 как это обязательное требование для формата сжатия текстур в экспорте действия, описанные ниже. Наконец, когда gerating mip-карты или текстуры наименьшее mip должны быть более 4 x 4.
<br>

|  Рекомендуемый размер текстуры  |  Размер текстуры max | Наименьшее Mip
|----|----|----|
|  512 x 512  |  4096 x 4096 | Макс. 4 x 4|

### <a name="albedo-base-color-map"></a>Карта albedo (базовый цвет)

Необработанные цвет без освещения информации. Эта карта содержит также отражающая способность и рассеянный сведения для исходного состояния системы (белый переключатель в схеме металлической) и рабочих областей insulator (черный в схеме металлической) соответственно.

### <a name="normal"></a>Обычный

Касательной обычный пространства карты

### <a name="roughness-map"></a>Неровности карты

Описывает microsurface объекта. Технический 1.0 это примерное smooth — черный 0,0. Эта карта предоставляет средства, которые наиболее символ как по-настоящему описывает области например חאכמזטע, отпечатки пальцев, стекле, grime и т.д.

### <a name="ambient-occlusion-map"></a>Карты окружения перекрытия

Сопоставление значений шкалы, изображающие областей перекрыто света, который блокирует отражений

### <a name="metallic-map"></a>Металлической карты

Сообщает шейдера, если что-то не исходного состояния системы или нет. Необработанные операционной системы = 1.0 белый исходного состояния системы не = 0.0 черный. Может существовать transitional серый значения, указывающие какие-либо, охватывающий необработанные исходного состояния системы, например грязи, но в целом это сопоставление должно быть только черного и белого.

## <a name="optimizations"></a>Оптимизация

Windows Mixed Reality домашней предлагает ряд оптимизаций на основе спецификации glTF core, определенных с помощью пользовательских расширений. В версиях Windows требуются эти оптимизации < = 1709 и рекомендуется использовать на более новых версиях Windows. Вы можете легко оптимизировать любой модели glTF 2.0 с помощью [Windows смешанной реальности активов преобразователь на сайте GitHub](https://github.com/Microsoft/glTF-Toolkit/releases). Это средство выполнит правильный текстуры упаковки и оптимизации, как указано ниже. Для общего использования мы рекомендуем использовать WindowsMRAssetConverter, но если требуется больший контроль над работой и хотели бы создать собственный конвейер оптимизации можно обратиться к подробную спецификацию ниже.  

### <a name="materials"></a>Материалы

Для улучшения времени в смешанной реальности сред Windows MR загрузки ОС может отображать сжатые текстуры DDS, упакованные в соответствии с текстуры, упаковки схемы, определенной в этом разделе. Текстуры DDS указываются с помощью [MSFT_texture_dds расширение](https://github.com/sbtron/glTF/tree/MSFT_lod/extensions/Vendor/MSFT_texture_dds). Сжатие текстур, настоятельно рекомендуется. 

#### <a name="hololens"></a>HoloLens

Возможности HoloLens под управлением смешанной реальности ожидать текстуры, чтобы быть упакованы с помощью программы установки 2-текстуры, с помощью следующей спецификации упаковки:
<br>

|  glTF свойство  |  Текстуры  |  Схема упаковки | 
|----------|----------|----------|
|  pbrMetallicRoughness  |  baseColorTexture  |  Красный (R), зеленого (G), синий (B) | 
|  [MSFT_packing_normalRoughnessMetallic](https://github.com/KhronosGroup/glTF/blob/master/extensions/2.0/Vendor/MSFT_packing_normalRoughnessMetallic/README.md)  |  normalRoughnessMetallicTexture  |  Обычный (группа Ресурсов), (B), неровности лаковых (A) | 


При сжатии текстуры DDS следующие сжатия ожидается на каждой карте:
<br>

|  Текстуры  |  Ожидаемый сжатия | 
|------|------|
|  baseColorTexture, normalRoughnessMetallicTexture |  BC7 | 

#### <a name="immersive-vr-headsets"></a>Иммерсивную (VR)

Основанные на ПК Windows Mixed Reality интерфейсы для иммерсивную (VR) ожидается, что текстуры, чтобы быть упакованы с помощью программы установки 3-текстуры, с помощью следующей спецификации упаковки:

##### <a name="windows-os--1803"></a>ОС Windows > = 1803

<br>

|  glTF свойство  |  Текстуры  |  Схема упаковки | 
|----------|----------|----------|
|  pbrMetallicRoughness  |  baseColorTexture  |  Красный (R), зеленого (G), синий (B) | 
|  [MSFT_packing_occlusionRoughnessMetallic](https://github.com/KhronosGroup/glTF/blob/master/extensions/2.0/Vendor/MSFT_packing_occlusionRoughnessMetallic/README.md)  |  occlusionRoughnessMetallicTexture  |  Occlusion (R) неровности (G), лаковых (B) | 
|  [MSFT_packing_occlusionRoughnessMetallic](https://github.com/KhronosGroup/glTF/blob/master/extensions/2.0/Vendor/MSFT_packing_occlusionRoughnessMetallic/README.md)  |  normalTexture  |  Обычный (группа Ресурсов) | 

При сжатии текстуры DDS следующие сжатия ожидается на каждой карте:
<br>

|  Текстуры  |  Ожидаемый сжатия | 
|------|------|
|  normalTexture  |  BC5 | 
|  baseColorTexture, occlusionRoughnessMetallicTexture  |  BC7 | 

##### <a name="windows-os--1709"></a>ОС Windows < = 1709
<br>

|  glTF свойство  |  Текстуры  |  Схема упаковки | 
|----------|----------|----------|
|  pbrMetallicRoughness  |  baseColorTexture  |  Красный (R), зеленого (G), синий (B) | 
|  [MSFT_packing_occlusionRoughnessMetallic](https://github.com/KhronosGroup/glTF/blob/master/extensions/2.0/Vendor/MSFT_packing_occlusionRoughnessMetallic/README.md)  |  roughnessMetallicOcclusionTexture  |  Roughness (R) лаковых (G), перекрытия (B) | 
|  [MSFT_packing_occlusionRoughnessMetallic](https://github.com/KhronosGroup/glTF/blob/master/extensions/2.0/Vendor/MSFT_packing_occlusionRoughnessMetallic/README.md)  |  normalTexture  |  Обычный (группа Ресурсов) | 

При сжатии текстуры DDS следующие сжатия ожидается на каждой карте:
<br>

|  Текстуры  |  Ожидаемый сжатия | 
|------|------|
|  normalTexture  |  BC5 | 
|  baseColorTexture, roughnessMetallicOcclusionTexture | BC7 |

### <a name="adding-mesh-lods"></a>Добавление сетки LODs

Windows MR использует узел geometry LODs для отображения трехмерных моделей с различными уровнями детализации, в зависимости от экрана покрытия. Хотя эта функция технически не является обязательной, настоятельно рекомендуется для всех средств. В настоящее время Windows поддерживает три уровня детализации. Текстур и значение по умолчанию — 0, представляющее высочайшего качества. Другие LODs нумеруются последовательно, например 1, 2 и get прогрессивно более низкое качество. [Windows смешанной реальности активов преобразователь](https://github.com/Microsoft/glTF-Toolkit/releases) поддерживает создание средств, которые соответствуют данной спецификации текстур и, принимая несколько glTF моделей и их объединения в один ресурс с допустимым текстур и уровнями. В следующей таблице приведены ожидаемые текстур и упорядочения и треугольник целевые объекты:
<br>

|  Уровень текстур и  |  Рекомендуемое число треугольник  |  Максимальное число треугольник | 
|-------|-------|-------|
|  ТЕКСТУР И 0 |  10,000 |  10,000 | 
|  ТЕКСТУР И 1 |  5,000  |  10,000 | 
|  ТЕКСТУР И 2 |  2,500  |  10,000 | 

При использовании LODs всегда укажите 3 текстур и уровней. Отсутствует LODs приведет к модели неожиданно отображалась как переключателей текстур и система отсутствующий текстур и уровень. glTF 2.0 не поддерживает LODs как часть спецификации core. LODs таким образом должен определяться с помощью [MSFT_LOD расширение](https://github.com/sbtron/glTF/tree/MSFT_lod/extensions/Vendor/MSFT_lod).

### <a name="screen-coverage"></a>Заполнение экрана

В Windows Mixed Reality, в зависимости от системы, обусловленных покрытия экрана, значение для каждого текстур и отображаются LODs. На более высоком уровне текстур и отображаются объекты, использующие в настоящее время большая часть пространство на экране. Заполнение экрана не является частью спецификации glTF 2.0 core и должен быть указан в разделе «дополнения» MSFT_ScreenCoverage [MSFT_lod расширение](https://github.com/sbtron/glTF/tree/MSFT_lod/extensions/Vendor/MSFT_lod).
<br>

|  Уровень текстур и  |  Рекомендуемый диапазон  |  Диапазон по умолчанию | 
|-------|-------|-------|
|  ТЕКСТУР И 0  |  100% - 50% |  .5 | 
|  ТЕКСТУР И 1 |  В разделе 50 – 20%  |  .2 | 
|  ТЕКСТУР И 2 |  В разделе 20 – 1%  |  .01 | 
|  ТЕКСТУР И 4  |  В разделе 1%  |  - | 

## <a name="animation-guidelines"></a>Рекомендации по анимации

> [!NOTE]
> Эта функция была добавлена как часть [обновления Windows 10 апреля 2018 г](release-notes-april-2018.md). В предыдущих версиях Windows, эти анимации не воспроизводится Однако они по-прежнему загрузится, если созданы в соответствии с инструкциями в этой статье.  

Домашняя страница смешанной реальности поддерживает glTF анимированных объектов на HoloLens и иммерсивную (VR). Если вы хотите активировать анимацию в модели, необходимо использовать модуль карты анимации на формат glTF. Это расширение позволяет активировать анимацию в glTF модели на основе наличия пользователей в мире, например запуск анимации, когда пользователь находится рядом с объектом, или при просмотре на него. Если объект glTF анимации, но не определяет триггеры анимации не воспроизводиться. В следующем разделе описывается один рабочий процесс для добавления этих триггеров в любой glTF анимированный объект.

### <a name="tools"></a>Инструменты
Во-первых скачайте следующие средства, если у вас их еще нет. Эти средства легко открыть любой модели glTF, предварительного просмотра, изменения и сохранения обратно как glTF или .glb:
1. [Visual Studio Code](https://code.visualstudio.com/)
2. [glTF средства для Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=cesium.gltf-vscode)


### <a name="opening-and-previewing-the-model"></a>Открытие и просмотр модели
Сначала откройте модель glTF в VSCode, перетащив файл .glTF в окно редактора. Обратите внимание, что у вас есть .glb вместо .glTF файл можно импортировать в VSCode, с помощью надстройки средства glTF загруженный. Перейти к «Вид -> палитру команд», а затем начните вводить в палитре команд «glTF» и выберите «glTF: Импорт из командной» которого появится всплывающее окно выбора файлов для импорта .glb с. 

После открытия модели glTF вы увидите в окне редактора JSON. Обратите внимание, что также можно просмотреть модель в динамической трехмерного просмотра с помощью, имя файла щелкните правой кнопкой мыши и выбрав команду «glTF: Предварительный просмотр трехмерной модели» ярлык команды в меню щелкните правой кнопкой мыши. 

### <a name="adding-the-triggers"></a>Добавление триггеров
Модель glTF JSON с помощью расширения сопоставления анимации добавляются триггеры анимации. Расширения сопоставления анимации общедоступна [с сайта GitHub](https://github.com/msfeldstein/glTF/blob/04f7005206257cf97b215df5e3f469d7838c1fee/extensions/Vendor/FB_animation_map/README.md) (Примечание: ЭТО РАСШИРЕНИЕ ЧЕРНОВИК). Чтобы добавить расширение для прокрутки модели только в конец файла glTF в редакторе и добавьте блок «extensionsUsed» и «расширения» в файл, если они еще не существуют. В разделе «extensionsUsed» вы добавите ссылку на расширение «EXT_animation_map» и в блоке «расширения» вы добавите сопоставлений анимации в модели.

Как было отмечено [в спецификации](https://github.com/msfeldstein/glTF/blob/04f7005206257cf97b215df5e3f469d7838c1fee/extensions/Vendor/FB_animation_map/README.md) определить триггеры анимации, используя строку «семантической» в список «анимация» из-за которого представляет собой массив индексов анимации. В следующем примере мы указали анимация должна воспроизводиться, пока пользователь gazing в объекте:

```json
  "extensionsUsed": [
    "EXT_animation_map"
  ],
  "extensions" : {
      "EXT_animation_map" : {
            "bindings": [
                {
                    "semantic": "GAZE",
                    "animations": [0]
                }
            ]
      }
  }
```
Следующую семантику триггеры анимации поддерживаются Windows Mixed Reality home.  
* «ВСЕГДА»: Постоянно цикл анимации
* «КОМПЬЮТЕР»: Замыкания на себя за весь период объект извлечен.
* «ВЗГЛЯДОМ»: Зациклен хотя проверяемый объект
* «БЛИЗОСТЬ»: Зациклен во время просмотра скоро истечет объекта
* «УКАЗЫВАЕТ»: Зациклен, пока пользователь указывает на объект

### <a name="saving-and-exporting"></a>Сохранение и экспорт
После внесения изменений в модель glTF, его можно сохранить непосредственно в качестве glTF или правой кнопкой мыши щелкнуть имя файла в редакторе и выберите «glTF: Экспорт в Командной (двоичный файл)» вместо этого экспортировать .glb. 

### <a name="restrictions"></a>Ограничения
Анимации не может быть длиннее 20 минут и не может содержать более чем 36,000 опорных кадров (20 минут 30 кадров в секунду). Кроме того при использовании целевого объекта morph основе анимации не превышает 8192 morph целевой вершины или меньше. Превышение эти несложные будет число анимированных ОС поддерживаются в Windows Mixed Reality дома. 

|Компонент|Максимум|
|-----|-----|
|Продолжительность|20 минут|
|Опорные кадры|36,000| 
|Morph целевой вершины|8192|

## <a name="gltf-implementation-notes"></a>Примечания по реализации glTF
Windows MR не поддерживает транспонирования geometry, отрицательное шкалах. Геометрия с отрицательным шкал вероятнее всего, приведет визуальных артефактов.

GlTF ресурса должен указывать на сцену по умолчанию, используя атрибут сцены к просмотру, MR Windows. Кроме того, загрузчик glTF Windows MR до версии [обновления Windows 10 апреля 2018 г.](release-notes-april-2018.md) **требует** методы доступа:
* Должен иметь минимальные и максимальные значения.
* Тип SCALAR, должен быть componentType UNSIGNED_SHORT (5123) или UNSIGNED_INT (5125).
* Тип VEC2 и VEC3 должен быть componentType FLOAT (5126).

Следующие свойства material использования из спецификации glTF 2.0 core, но не требуется:
* baseColorFactor, metallicFactor, roughnessFactor
* baseColorTexture: Должно указывать текстуры, хранящихся в dds.
* emissiveTexture: Должно указывать текстуры, хранящихся в dds.
* emissiveFactor
* alphaMode

Следующие свойства material игнорируются из спецификации core:
* Все Multi-UVs
* metalRoughnessTexture: Вместо этого необходимо использовать Microsoft оптимизированных для операций упаковки текстуры, см. ниже
* normalTexture: Вместо этого необходимо использовать Microsoft оптимизированных для операций упаковки текстуры, см. ниже
* normalScale
* occlusionTexture: Вместо этого необходимо использовать Microsoft оптимизированных для операций упаковки текстуры, см. ниже
* occlusionStrength

Windows MR не поддерживает примитивных режим линий и точек. 

Поддерживается только один атрибут UV вершин.

## <a name="additional-resources"></a>Дополнительные ресурсы
* [glTF экспорта и преобразователи типов](https://github.com/KhronosGroup/glTF#converters-and-exporters)
* [glTF Toolkit](https://github.com/Microsoft/glTF-Toolkit)
* [glTF 2.0 спецификации](https://github.com/KhronosGroup/glTF/blob/master/README.md)
* [Microsoft glTF спецификации текстур и расширения](https://github.com/KhronosGroup/glTF/blob/master/extensions/2.0/Vendor/MSFT_lod/README.md)
* [Смешанный реальности текстуры упаковки расширения спецификации ПК](https://github.com/KhronosGroup/glTF/blob/master/extensions/2.0/Vendor/MSFT_packing_occlusionRoughnessMetallic/README.md)
* [Смешанный реальности текстуры упаковки расширения спецификации HoloLens](https://github.com/KhronosGroup/glTF/blob/master/extensions/2.0/Vendor/MSFT_packing_normalRoughnessMetallic/README.md)
* [Спецификация расширения glTF текстуры DDS Microsoft](https://github.com/KhronosGroup/glTF/tree/master/extensions/2.0/Vendor/MSFT_texture_dds)

## <a name="see-also"></a>См. также

* [Реализация средств запуска трехмерных приложений (приложения UWP)](implementing-3d-app-launchers.md)
* [Реализация средств запуска трехмерных приложений (приложения Win32)](implementing-3d-app-launchers-win32.md)
* [Навигация по дому с технологией Windows Mixed Reality](navigating-the-windows-mixed-reality-home.md)
