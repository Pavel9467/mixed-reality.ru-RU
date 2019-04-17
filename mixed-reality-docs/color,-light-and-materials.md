---
title: Цвет, свет и материалы
description: Проектирование содержимое для смешанной реальности требует тщательного анализа цвет освещения и материалы для каждого из визуальных активов, используемый в интерфейсе.
author: mavitazk
ms.author: pinkb
ms.date: 03/21/2018
ms.topic: article
keywords: Windows Mixed Reality, разработки, цвет, свет, материалов
ms.openlocfilehash: 3f8ee8edfe4cbbaf8a55b3c4a9125f752823be9c
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59601379"
---
# <a name="color-light-and-materials"></a>Цвет, свет и материалы

Проектирование содержимое для смешанной реальности требует тщательного анализа цвет освещения и материалы для каждого из визуальных активов, используемый в интерфейсе. Эти решения могут быть эстетически целей, например, использование свет и материалы для устанавливают тон иммерсивных среды, и функциональной точки зрения, как с помощью впечатляющих цветов, чтобы оповестить пользователей о предстоящем действия. Каждое из этих решений необходимо взвесить возможности и ограничения работы на целевом устройстве.

Ниже приведены рекомендации для подготовки к просмотру ресурсов на иммерсивных и holographic гарнитур. Многие из них тесно связаны с другим техническим областям и список связанных субъектов можно найти в [см. также](color,-light-and-materials.md#see-also) в конце этой статьи.

## <a name="rendering-on-immersive-vs-holographic-devices"></a>Подготовка к просмотру в иммерсивных и holographic устройств

Содержимое, подготавливается к просмотру в иммерсивную отобразится визуально отличаться по сравнению с содержимое отображается в holographic гарнитур. Хотя обычно иммерсивную отображения содержимого, так же как и следовало ожидать на двумерном экране, holographic гарнитуры, например HoloLens последовательных цвета, сквозная RGB отображает голограммы подготавливает к просмотру.

Всегда имеют время протестировать holographic опытом holographic гарнитуры. Отображение содержимого, даже если она создана специально для holographic устройств будут различаться как видно на вторичный мониторах, моментальные снимки и в представлении spectator. Не забудьте сильна взаимодействия с устройством, за из всех сторон (а также выше и ниже) и тестирование освещение голограммы способ отображения содержимого. Обязательно протестируйте в диапазон яркости параметров на устройстве, так как маловероятно, все пользователи будут обмениваться принято значение по умолчанию, а также ряд различных условиях освещения.

## <a name="fundamentals-of-rendering-on-holographic-devices"></a>Основные принципы подготовки к просмотру на holographic устройствах
* **Holographic устройства имеют аддитивные отображает** — голограммы создаются путем добавления свет на свет из реального мира — белый яркой, будет отображаться при черный будет отображаться прозрачным.
* **Влияние цветов зависит от среду** — существует множество различных освещении в комнате пользователя. Создание содержимого с соответствующими уровнями контрастности для ясности.
* **Избегайте динамических освещения** — голограммы, которые равномерно включаются в holographic возможности наиболее эффективны. С помощью дополнительных динамических световых скорее всего будет предоставляют более широкие возможности мобильных шейдеров.

## <a name="designing-with-color"></a>Проектирование с цветом

Из-за природы аддитивные отображает некоторые цвета может отличаться на вывод разделов, holographic. Некоторые цвета откроется в средах освещения, хотя другим пользователям будет отображаться как менее важные. "Холодный" цвета, как правило, направлены в фоновом режиме, хотя «горячего» резервирования цвета переводу на передний план. При просмотре цвета в своим опытом, учитывайте следующие факторы:
* **Цветовой гаммы** -HoloLens выигрывает от «обширном» цвета, концептуально сходная с Adobe RGB. В результате некоторые цвета может привести к различные возможности и представление в устройство.
* **Гамма** -яркости и контрастности подготовленного изображения варьируются у разных устройств иммерсивный и holographic. Чтобы сделать более или менее яркий цвета и теней, "темных" областях часто появляются таких различий в устройствах.
* **Цветоделение** -также называется «разбиение цвет» или «цветной каймы», цветоделение чаще всего возникает с перемещением голограммы (включая курсора) Если пользователь отслеживает объекты с их глаза.
* **Цвет единообразие** -обычно голограммы подготавливаются к просмотру яркой достаточно, чтобы они поддерживать единообразие цвета, независимо от того, фон. Больших областей может стать результат. Избегайте больших участков ярко, сплошной цвет.
* **Подготовка к просмотру светлых цветов** -белым цветом, появится очень ярко- и следует использовать с осторожностью. В большинстве случаев рекомендуется значение белого вокруг R 235 G 235 B 235. Больших ярко-областей может привести к discomfort пользователя.

**Подготовка к просмотру темные цвета**

Из-за природы аддитивные отображает прозрачным темные цвета. Сплошной черной объекта будет отображаться не отличается от реального мира. Альфа-канал см. ниже. Чтобы предоставить внешний вид «black» попробуйте очень темно-серый значение RGB, например 16,16,16.

![Обычный и широкая цветовая палитра](images/640px-widegamut.png)<br>
*Обычный и широкая цветовая палитра*

## <a name="technical-considerations"></a>Технические особенности
* **Присвоение псевдонима** -быть предусмотрительным псевдонимы, массивы или «лестницы шаги», где граница голограмма геометрического объекта совпадает с реального мира. Использование текстур с подробностями можно к ухудшению этот эффект. Текстуры должны быть сопоставлены и включена фильтрация. Рассмотрите возможность плавный переход края голограммы или добавление текстуры, создает обрамление черные границы вокруг объектов. Избегайте тонкой geometry, где это возможно.
* **Альфа-канал** -альфа-канала до полной прозрачности для всех частей, где не выполняется отрисовка голограмма необходимо очистить. При извлечении изображений и видео с устройства или с помощью представления Spectator, а альфа-неопределенный потенциальных клиентов в визуальных артефактов.
* **Текстуры Размытие** — поскольку горит аддитивны в holographic отображает, желательно избежать больших участков ярко, сплошной цвет, как они часто дают предполагаемого визуальный эффект.

## <a name="storytelling-with-light-and-color"></a>Создание сюжетов свет и цвет

Свет и цвет поможет сделать ваши голограммы более естественным образом отображаются в пользователя среды как руководство и помочь для пользователя. Для работы в holographic учитывайте следующие факторы при просмотре освещения и цвет:
* **Виньетирование** -эффект «виньетирования», на который затемняется материалы помогут сосредоточить внимание пользователя по центру поле зрения. Этот эффект затемняет голограмма материала на некоторые radius от пользователя взглядом вектора. Обратите внимание на то, что это может использоваться при попытке пользователя просмотреть голограммы углового наклонный или смысл.
* **Выделение** -привлечь внимание к объектов или точки взаимодействия, контрастные цвета, яркость и освещения. Более подробно изучить методы освещения в сюжетов, см. в разделе [Cinematography пикселей - освещения подход для компьютерной графике](http://media.siggraph.org/education/cgsource/Archive/ConfereceCourses/S96/course30.pdf).

![Используйте цвет для отображения выделения для сюжетов, приведенные здесь элементы в сцене из фрагментов.](images/640px-fragments.jpg)<br>
*Использование цветов для отображения выделения для сюжетов, приведенные здесь элементы в сцене из [фрагментов](https://www.microsoft.com/p/fragments/9nblggh5ggm8).*

## <a name="see-also"></a>См. также
* [Разделение цвет](hologram-stability.md#color-separation)
* [Голограммы](hologram.md)
* [Язык проектирования Microsoft - цвет](https://www.microsoft.com/design/color)
* [Универсальная платформа Windows - цвет](https://docs.microsoft.com/windows/uwp/style/color)