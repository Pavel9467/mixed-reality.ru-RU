---
title: Наведение и фиксация с использованием рук
description: Общие сведения о модели ввода с наведением и фиксацией
author: caseymeekhof
ms.author: cmeekhof
ms.date: 04/05/2019
ms.topic: article
ms.localizationpriority: high
keywords: Mixed Reality, interaction, design, hololens, hands, far, point and commit
ms.openlocfilehash: 30f85d2bb455abab3a533e0a829b4fba8cea0a7a
ms.sourcegitcommit: f20beea6a539d04e1d1fc98116f7601137eebebe
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66402383"
---
# <a name="point-and-commit-with-hands"></a>Наведение и фиксация с использованием рук
Наведение и фиксация с использованием рук представляет собой модель ввода, которая позволяет пользователям нацеливаться на двухмерное содержимое и трехмерные объекты, а также выделять их и управлять ими на расстоянии. Этот способ "удаленного" взаимодействия характерен только для смешанной реальности и не является естественным способом взаимодействия людей с реальным миром. Например, в фильме о супергероях *Люди Икс* персонаж [Магнето](https://en.wikipedia.org/wiki/Magneto_(comics)) способен дотягиваться до удаленных объектов и манипулировать ими на расстоянии с использованием рук. Это не то, что люди могут делать в реальности. В HoloLens (дополненной реальности) и смешанной реальности (виртуальной реальности) мы вооружаем пользователей этой магической силой, преодолевающей физическое ограничение реального мира не только для отличной работы с голографическим содержимым, но и для более эффективного взаимодействия.

## <a name="device-support"></a>Поддержка устройств

Модель ввода | [HoloLens (1-го поколения)](https://docs.microsoft.com/en-us/windows/mixed-reality/hololens-hardware-details) | HoloLens 2 | [Иммерсивные гарнитуры](https://docs.microsoft.com/en-us/windows/mixed-reality/immersive-headset-hardware-details) |
| ---------| -----| ----- | ---------|
Наведение и фиксация с использованием рук | ❌ Не поддерживается | ✔ Рекомендуется | ✔ Рекомендуется

Модель наведения и фиксации, также известная как "руки на расстоянии", — одна из появившихся возможностей, использующих новую систему отслеживания рук. Это основная модель ввода в иммерсивных гарнитурах, использующих контроллеры движений.

## <a name="hand-rays"></a>Лучи рук

В HoloLens 2 мы разработали луч руки, который исходит из центра ладони. Этот луч рассматривается как продолжение руки. Курсор в виде кольца присоединяется к концу луча, указывая расположение, в котором луч пересекается с целевым объектом. После этого объект, на котором размещается курсор, может получать жестовые команды от руки.

Эта базовая жестовая команда запускается действием касания с помощью большого и указательного пальца. Используя луч руки для наведения и фиксации, пользователи могут активировать кнопку или гиперссылку в веб-содержимом. С помощью более сложных жестов пользователи могут переходить по веб-содержимому и управлять трехмерными объектами на расстоянии. Визуальный дизайн луча руки также должен реагировать на эти состояния наведения и фиксации, как описано и показано ниже. 

* В состоянии *указания* луч представлен штриховой линией, а курсор — в форме кольца.
* В состоянии *фиксации* луч превращается в сплошную линию, а курсор сжимается в точку.

![](images/Hand-Rays-720px.jpg)

## <a name="transition-between-near-and-far"></a>Переход между "близко" и "далеко"

Мы разработали луч, поступающий из центра ладони, что освобождает пять пальцев для более манипулятивных жестов, таких как сжатие и захват. Благодаря этому вам не нужно направлять луч с помощью определенных жестов, таких как наводка указательным пальцем. При такой структуре мы создаем только одну ментальную модель, поддерживающую один и тот же набор жестов руками для взаимодействия вблизи и вдали. Для управления объектами на различных расстояниях можно использовать один и тот же жест захвата. Вызов лучей происходит автоматически и зависит от приближенности:

*  Если объект находится на расстоянии вытянутой руки (примерно 50 см), лучи автоматически отключаются, побуждая к близкому взаимодействию.
*  Если объект находится дальше, чем на расстоянии 50 см, лучи включаются. Переход должен быть плавным и легким.

![](images/Transition-Between-Near-And-Far-720px.jpg)

## <a name="2d-slate-interaction"></a>Взаимодействие с двумерным экраном

Двумерный экран — это голографический контейнер с содержимым двумерных приложений, таких как веб-браузер. Концепция разработки удаленного взаимодействия с двухмерным экраном заключается в использовании лучей рук для наведения и касании для выделения. После наведения на цель луча руки пользователи могут с помощью касания активировать гиперссылку или кнопку. Они могут использовать одну руку для касания и захвата, чтобы прокрутить содержимое экрана вверх и вниз. Относительное движение при использовании обеих рук для касания и захвата может увеличить и уменьшить масштаб содержимого экрана.

При нацеливании луча руки на углы и края появляется отображение ближайших возможностей для манипуляции. Путем захвата и перетаскивания возможностей для манипуляции пользователи могут выполнить равномерное масштабирование с помощью угловых возможностей и адаптировать экран с помощью крайних возможностей. Путем захвата и перетаскивания голографической панели в верхней части двухмерного экрана пользователи могут переместить весь экран.

![](images/2D-Slate-Interaction-Far-720px.jpg)

Для манипуляции самим двумерным экраном:<br>

* Пользователи нацеливают луч руки на углы и края, чтобы появилось отображение ближайших возможностей для манипуляции. 
* Применяя жест манипуляции к возможности, пользователи могут выполнить равномерное масштабирование с помощью угловых возможностей и адаптировать экран с помощью крайних возможностей. 
* Применяя жест манипуляции к голографической панели в верхней части двухмерного экрана, пользователи могут переместить весь экран.<br>

<br>

## <a name="3d-object-manipulation"></a>Манипуляция трехмерными объектами

В непосредственной манипуляции пользователи могут манипулировать трехмерными объектами двумя способами: манипуляция на основе возможностей и манипуляция без использования возможностей. В модели наведения и фиксации пользователи могут выполнять точно такие же задачи с помощью лучей рук. Дополнительное обучение не требуется.<br>

### <a name="affordance-based-manipulation"></a>Манипуляция на основе возможностей
Пользователи используют лучи рук, чтобы навести и выявить ограничивающую рамку и возможности для манипуляции. Пользователи могут применить жест манипуляции к ограничивающей рамке, чтобы переместить весь объект, к возможностям по краям, чтобы повернуть, и возможностям в углах, чтобы выполнить равномерное масштабирование. <br>

![](images/3D-Object-Manipulation-Far-720px.jpg) <br>


### <a name="non-affordance-based-manipulation"></a>Манипуляция без использования возможностей
Пользователи наводят лучи рук, чтобы появилось отображение ограничивающей рамки, а затем к нему непосредственно применяют жесты манипуляции. При использовании одной руки перемещение и вращение объекта связаны с движением и ориентацией руки. При использовании обеих рук пользователи могут перемещать, масштабировать и вращать объект в соответствии с относительными движениями обеих рук.<br>

<br>

## <a name="instinctual-gesturers"></a>Инстинктивные жесты
Концепция инстинктивных жестов для наведения и фиксации аналогична непосредственной манипуляции. Жесты, которые пользователи могут применять к трехмерному объекту, определяются структурой возможностей пользовательского интерфейса. Например, небольшая контрольная точка может побуждать пользователей сжать объект с помощью большого и указательного пальцев, в то время как для захвата объекта большего размера пользователь может предпочесть использовать все 5 пальцев.

![](images/Instinctual-Gestures-Far-720px.jpg)<br>

## <a name="symmetric-design-between-hands-and-6-dof-controller"></a>Симметричный дизайн для работы с помощью рук и контроллеров с шестью степенями свободы 
Концепция наведения и фиксации для удаленного взаимодействия изначально была создана и определена для Портала смешанной реальности (MRP), где пользователь надевает иммерсивную гарнитуру и работает с трехмерными объектами через контроллеры движений. Контроллеры движений выпускают лучи для наведения на дальние объекты и манипулирования ими. На контроллерах есть кнопки для выполнения различных действий. Мы используем модель взаимодействия с помощью лучей и прикрепляем их к обеим рукам. При такой симметричной структуре пользователям, знакомым с MRP, не понадобится изучать другую модель взаимодействия для удаленного наведения и манипуляции при использовании HoloLen 2 и наоборот.    

![](images/Symmetric-Design-For-Rays-720px.jpg)<br>

## <a name="instinctual-gestures"></a>Инстинктивные жесты

![](images/Instinctual-Gestures-Far-720px.jpg)

## <a name="see-also"></a>См. также
* [Направление головы и фиксация](gaze-and-commit.md)
* [Непосредственное манипулирование с использованием рук](direct-manipulation.md)
* [Инстинктивное взаимодействие](interaction-fundamentals.md)

