---
title: Нацеливание взглядом
description: Все взаимодействия построены на базе возможность пользователя целевой элемент, на который они хотят взаимодействовать с ними независимо от входного модальность.
author: cre8ivepark
ms.author: jennyk
ms.date: 02/24/2019
ms.topic: article
keywords: Смешанный реальность, взглядом, взглядом, предназначенные для взаимодействия, проектирование
ms.openlocfilehash: c3225e27331f8afcda65469eb84fe5470bf6ee8c
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59600679"
---
# <a name="gaze-targeting"></a>Нацеливание взглядом

Все взаимодействия построены на базе возможность пользователя целевой элемент, на который они хотят взаимодействовать с ними независимо от входного модальность. В Windows Mixed Reality, это обычно делается с помощью взглядом пользователя.

Чтобы разрешить пользователю для успешной работы с помощью средств, системы вычисляемые объяснение намерение пользователя, а на фактический намерение пользователя, необходимо согласовать как как можно точнее. Степень, что система воспринимает необходимые действия пользователя правильно, производительности и повышает степень удовлетворенности улучшает.

## <a name="device-support"></a>Поддержка устройств

<table>
<tr>
<th>Компонент</th><th style="width:150px"> <a href="hololens-hardware-details.md">HoloLens (1-го поколения)</a></th><th style="width:150px">HoloLens 2</th><th style="width:150px"> <a href="immersive-headset-hardware-details.md">Иммерсивную</a></th>
</tr><tr>
<td> Нацеливание взглядом</td><td style="text-align: center;"> ✔️</td><td style="text-align: center;"> ✔️</td><td style="text-align: center;">✔️ </td>
</tr><tr>
<td> Предназначенные для глаз</td><td style="text-align: center;"></td><td style="text-align: center;"> ✔️</td><td style="text-align: center;"></td>
</tr>
</table>

> [!NOTE]
> Дополнительные рекомендации, относящиеся к HoloLens 2 [ожидается в ближайшее время](index.md#news-and-notes).

## <a name="target-sizing-and-feedback"></a>Изменение размера целевого и отзывы

Вектор взглядом показал многократно использоваться для нацеливания на нормально, но часто лучше всего работает для валовой выбора целевой платформы (получении большего целевые объекты). Минимальное целевое размеры градусов 1 – 1.5 должен позволять действия успешно пользователя в большинстве случаев на то, что целевые объекты 3 градусов часто позволяют для увеличения скорости. Обратите внимание, что размер, что целевые Пользователи эффективно 2D области, даже для трехмерных элементов — независимо от проекции направлена их следует указывать область. Предоставление некоторые ключевые подсказки, что элемент является «active» (что он предназначен для платформы он) будут очень полезны — это могут быть лечение видимым «при наведении указателя» эффекты, аудио основные особенности или щелчков мышью, такие как, или снимите выравнивание курсора с элементом.

![Размер оптимальной цели на расстоянии 2 средства измерения](images/gazetargeting-size-1000px.jpg)<br>
*Размер оптимальной цели на расстоянии 2 средства измерения*

![Пример выделения взглядом целевого объекта](images/gazetargeting-highlighting-640px.jpg)<br>
*Пример выделения взглядом целевого объекта*

## <a name="target-placement"></a>Целевой объект размещения

Пользователи часто смогут находить элементы пользовательского интерфейса, очень высокое или очень мало расположением в их поля зрения, сосредоточившись большую часть их внимания на областях вокруг их основное внимание (обычно примерно на уровне глаз). Размещение Большинство целевых объектов в некоторые разумные band уровне глаз может помочь. Учитывая тенденцию для пользователей сосредоточиться на относительно небольшой visual области в любое время (attentional конус компьютерного зрения — примерно 10 градусов), группируя элементы пользовательского интерфейса степень, что они концептуально связаны могут использовать цепочек внимания поведения из элемента к элементу, как пользователь перемещает их взглядом через область. При разработке пользовательского интерфейса, имейте в виду потенциальные больших вариантов в поле зрения между HoloLens и иммерсивную.

![Пример сгруппированных элементов пользовательского интерфейса для упрощения взглядом, в обозревателе Galaxy](images/gazetargeting-grouping-1000px.jpg)<br>
*Пример сгруппированных элементов пользовательского интерфейса для упрощения взглядом, в обозревателе Galaxy*

## <a name="improving-targeting-behaviors"></a>Улучшение поведения выбора целевой платформы

Если намерения пользователя, на что-то может быть определено (или приблизительно тесно), может быть очень полезно принять «промаха» попыток во взаимодействие, как будто они были затронуты правильно. Существует несколько эффективных методов, которые могут быть включены в возможности смешанной реальности.

### <a name="gaze-stabilization-gravity-wells"></a>Стабилизации взглядом («тяжести wells»)

Это должно быть включено большинство или все время. Этот метод удаляет естественным head/горлышка ухудшению качества сигнала, которые пользователи могут иметь. Также перемещения из-за поиск говоря поведения.

### <a name="closest-link-algorithms"></a>Ближайший алгоритмы ссылку

Они лучше всего работают в областях с разреженным интерактивное содержимое. Если существует высокая вероятность того, вы можете определять, что пользователь пытался взаимодействовать с, можно дополнить их определения возможностей, просто при условии, что некоторый уровень намерение.

### <a name="backdatingpostdating-actions"></a>Backdating postdating действия

Этот механизм полезен в задач, требующих скорости. При пользователя, проходящего через ряд маневры предназначенных для активации на скорости, его можно использовать некоторые намерения и разрешить *пропустили действия* для целевых объектов, которые пользователь имеет в фокус немного до или немного после (tap) 50 мс до и после был эффективен для раннего тестирования).

### <a name="smoothing"></a>Сглаживание

Этот механизм полезен для перемещений путь, уменьшая небольшая дрожание/Иванин из-за характеристик головной движение. Когда сглаживания через путь движения, smooth размер/расстояние движения, а не по времени

### <a name="magnetism"></a>Магнитного

Этот механизм может рассматриваться как более Общая версия «Ближе всего связать» алгоритмы - рисования курсора к целевой объект, или просто увеличить hitboxes (ли визуально или нет) как пользователи подход, скорее всего, целевые объекты, с помощью знание интерактивных макет лучше намерения пользователя подход. Это может быть особенно эффективна для небольших целевых объектов.

### <a name="focus-stickiness"></a>Закрепление фокус

При определении которого ближайшие интерактивные элементы, чтобы перевести фокус, предоставляют сдвиг к элементу, который в настоящее время заточен. Это позволит уменьшить многоязыковых интерфейсах фокус, переключение поведений с плавающей запятой в средней точки между двумя элементами с естественным шумом.

## <a name="see-also"></a>См. также
* [Жесты](gestures.md)
* [Проектирование голоса](voice-design.md)
* [Курсоры](cursors.md)