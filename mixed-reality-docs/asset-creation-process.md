---
title: Процесс создания ресурса
description: Руководство по созданию средств для работы в смешанной реальности.
author: paseb
ms.author: paseb
ms.date: 03/21/2018
ms.topic: article
keywords: средства, создания, процесс, бюджет, многоугольники, текстуры, построители текстур, производительности
ms.openlocfilehash: 513a9856ac35e4229cfb7bc8bcb92d9d6a152980
ms.sourcegitcommit: f20beea6a539d04e1d1fc98116f7601137eebebe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66692300"
---
# <a name="asset-creation-process"></a>Процесс создания ресурса

Смешанная реальность Windows основана на десятилетий инвестиции, которые корпорация Майкрософт внесла в DirectX. Это означает, что все разработчики опыт и навыки создания трехмерной графики продолжает быть ценна для HoloLens.

Ресурсы, созданные для проекта могут быть множество форм и форм. Может состоять из ряда текстуры и изображения, аудио, видео, 3D-моделей и анимации. Мы не может начинаться так охватить все средства, которые можно создавать разные ресурсы, используемые в проекте. В этой статье мы рассмотрим методы создания трехмерных активов.

![Концепция, создания, интеграции и итерации потока](images/concept-creation-integration-iteration-flow-640px.jpg)<br>
*Концепция, создания, интеграции и итерации потока*

## <a name="things-to-consider"></a>Моменты, которые следует принять во внимание

При просмотре в интерфейсе, вы пытаетесь создать представьте его как **бюджета** что вы смогли потратить с целью создания получения наилучших результатов. Не обязательно жесткие ограничения на количество **многоугольники** или **типов материалов** использовать в ваши ресурсы, но более бюджетные набор компромиссов.

Ниже приведен пример бюджета вашими потребностями. Производительность обычно не является единой точкой сбоя, но смерть от тысячи порезов на se.
<br>

<table style="float:right; margin-left: 10px;">
<tr>
<th style="text-align:left;"><b>Активы</b></th><th style="text-align:right;"> ЦП</th><th> Графический процессор</th><th> Память</th>
</tr><tr>
<td> Многоугольники</td><td> 0%</td><td> 5%</td><td> 10 %</td>
</tr><tr>
<td> Текстуры</td><td> 5%</td><td> 15%</td><td>25%</td>
</tr><tr>
<td> Шейдеры</td><td> 15%</td><td> 35 %</td><td> 0%</td>
</tr><tr>
<td> <b>Dynamics</b></td><td></td><td></td><td></td>
</tr><tr>
<td> Физика</td><td> 5%</td><td> 15%</td><td> 0%</td>
</tr><tr>
<td> Освещение в реальном времени</td><td> 10 %</td><td> 0%</td><td> 0%</td>
</tr><tr>
<td> Media (аудио и видео)</td><td> -</td><td> 15%</td><td> 25%</td>
</tr><tr>
<td> Логика/сценария</td><td> 25%</td><td> 0%</td><td> 5%</td>
</tr><tr>
<td> Общим накладным расходам</td><td> 5%</td><td> 5%</td><td> 5%</td>
</tr><tr>
<td> <b>Общее число</b></td><td> <b>65%</b></td><td> <b>90%</b></td><td> <b>70%</b></td>
</tr>
</table>

**Общее число ресурсов**
* Сколько средств активны в сцене?

**Сложность средств**
* Сколько треугольники / многоугольники?
* Насколько сложным шейдера?

Разработчики и художники нужно проанализировать возможности устройства и графики. Microsoft HoloLens обладает всеми вычислительных ресурсов и графики, встроенный в устройство. Он использует возможности, которые доступны разработчикам на мобильной платформе.

Процесс создания ресурсов аналогичен для всех ли целевой платформой является интерфейс для [holographic устройство или устройство иммерсивных](mixed-reality.md#the-mixed-reality-spectrum). Следует Обратите внимание, является возможность устройства, как упоминалось выше, а также масштабирования, так как вы увидите реального мира в смешанной реальности, требуется сохранить правильный масштаб на основе опыта. 

## <a name="authoring-assets"></a>Средства разработки

Мы начнем с способы получения средств для проекта:
1. Создание средств (Создание и настройка средств и записать объект)
2. Приобретение ресурсов (через Интернет для средства в приобретение)
3. Перенос ресурсов (используя существующие ресурсы)
4. Аутсорсинг активы (Импорт средств сторонних производителей)

### <a name="creating-assets"></a>Создание ресурсов

**Средства разработки**<br>
Сначала можно создать собственные ресурсы в несколько разных способов. 3D — использование количество приложений и средств для создания моделей, которые состоят из **сетки**, **текстуры**, и **материалы**. Затем он сохраняется в формате, который мог быть импортирован или используемых графики, используемых приложением, таких как **. FBX** или **. OBJ**. Любой инструмент, который создает модели, которая поддерживает модуль выбранного графики будет работать на **HoloLens**. Среди 3D исполнители многие решили использовать [Autodesk Maya который сам является возможность использовать HoloLens](https://www.youtube.com/watch?v=q0K3n0Gf8mA) для преобразования создаются ресурсы способом. Если вы хотите получить что-то в быстрого можно также использовать [3D построитель](https://developer.microsoft.com/windows/hardware/3d-print/3d-builder-resources) , который поставляется вместе с Windows для экспорта. OBJ для использования в приложении.

**Объект записи**<br>
Есть также параметр для записи объектов в трехмерном пространстве. Записи неодушевленный в трехмерном пространстве и их редактирования с программным обеспечением Создание цифрового содержимого все более популярного с развитием трехмерной печати. С помощью **Kinect 2** датчика и [3D построитель](https://developer.microsoft.com/windows/hardware/3d-print/3d-builder-resources) функции записи можно использовать для создания ресурсов из реальных объектов. Это также [набор средств](https://en.wikipedia.org/wiki/Comparison_of_photogrammetry_software) делать то же самое с **photogrammetry** путем обработки количества образов для внакидку вместе и сетки и текстуры.

### <a name="purchasing-assets"></a>Приобретение ресурсов

Другой прекрасный вариант — приобрести средства для работы. Существует множество средств доступны через службы например [Unity Asset Store](https://www.assetstore.unity3d.com/) или [TurboSquid](http://www.turbosquid.com/) среди других.

При приобретении активы от третьих сторон, всегда можно проверить следующее:
* **Что такое число poly?**
  * Вписывается в пределах вашего бюджета?
* **Существуют уровни детализации (LODs) для модели?**
  * Уровень детализации модели можно масштабировать подробные сведения о модели для повышения производительности.
* **Доступна ли исходный файл?**
  * Обычно не входит в состав [Unity Asset Store](https://www.assetstore.unity3d.com/) , но всегда включены со службами, например [TurboSquid](http://www.turbosquid.com/).
  * Без исходного файла не будет иметь возможность изменять ресурс.
  * Убедитесь, что указан исходный файл можно импортировать по 3D-инструменты.
* **Знать, что вы получите**
  * Предоставляются ли анимации?
  * Обязательно ознакомьтесь со списком содержимое ресурса, который приобретения.

### <a name="porting-assets"></a>Перенос ресурсов

В некоторых случаях будет передаваться существующие ресурсы, которые изначально были созданы для других устройств и различных приложений. В большинстве случаев эти ресурсы можно преобразовать в форматы, которые совместимы с графики, приложение их использует.

При переносе ресурсов для использования в приложении HoloLens требуется задайте следующие вопросы:
* **Можно импортировать непосредственно или должны быть преобразованы в другой формат?** Проверьте формат, куда импортируются с графики, которую вы используете.
* **Если преобразование в формате, совместимом ничего теряется?** Иногда сведения могут быть потеряны или импорт может привести к артефакты, которые должны быть очищены в трехмерном пространстве, средство разработки.
* **Что такое треугольники / многоугольники count для ресурса?** На основе бюджета для приложения можно использовать [Simplygon](https://www.simplygon.com/) или аналогичные инструменты для decimate (процедурному или вручную уменьшение числа poly) исходного средства в соответствии с бюджетом приложений.

### <a name="outsourcing-assets"></a>Аутсорсинг активы

Другой вариант для крупных проектов, которые требуются дополнительные ресурсы, чем команды — все необходимое для создания — передать функции создания ресурса. Процесс аутсорсинг включает в себя поиск справа studio или агентства, которая специализируется в средствах аутсорсинг. Это может быть наиболее затратный, но также быть самый гибкий в вы получаете.
* **Четко определить, что запрос**
  * Укажите как можно больше подробностей
  * Передний план, на стороне и задней концепция образов
  * Справочник по активов отображение картинок в контексте
  * Масштабирование объекта (обычно это значение задается в сантиметрах)
* **Укажите бюджет**
  * Диапазон количества Poly
  * Число текстур
  * Построитель текстур (для Unity и HoloLens, следует всегда по умолчанию мобильные шейдеры сначала)
* **Ознакомьтесь с затратами на**
  * Что такое политика аутсорсинг для запросов на изменение

Аутсорсинг может работать очень хорошо зависимости проектов временной шкалы, но требует дополнительные контроль, чтобы гарантировать, что вы получаете правой ресурсы, необходимые в первый раз.
