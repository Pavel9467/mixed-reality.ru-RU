---
title: Общие возможности в смешанной реальности
description: Holographic приложения могут совместно использовать Пространственные привязки из одного HoloLens в другую, включение пользователей для подготовки к просмотру голограмма в том же месте, в реальном мире на нескольких устройствах.
author: thetuvix
ms.author: grbury
ms.date: 02/10/2019
ms.topic: article
keywords: опытом, смешанный реальность, голограмма, пространственных привязки, несколькими пользователями, с несколькими
ms.openlocfilehash: b27da1e73c927a26e33746cd2db08e67c6f70acc
ms.sourcegitcommit: f7fc9afdf4632dd9e59bd5493e974e4fec412fc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2019
ms.locfileid: "59605133"
---
# <a name="shared-experiences-in-mixed-reality"></a>Общие возможности в смешанной реальности

Нет необходимости голограммы оставаться частный только одному пользователю. Holographic приложения могут совместно использовать [пространственных привязки](coordinate-systems.md) из одного HoloLens, устройстве iOS или Android в другой, что позволяет пользователям для подготовки к просмотру голограмма в том же месте, в реальном мире на нескольких устройствах.

## <a name="six-questions-to-define-shared-scenarios"></a>Шесть вопросов для определения общих сценариев

Прежде чем начать проектирование для общего опыта при работе, важно определить целевые сценарии. Эти сценарии помогают уточнить, что вы проектирование и установления общего словаря для сравнения и сравните возможности, необходимые в интерфейсе. Основные сведения о данной проблеме core и различные методы для решения, является ключом к зависящих от него возможностей, присущих этот новый носитель.

Через внутренний прототипы и работы с данными из наших HoloLens партнерскими агентствами мы создали шесть вопросов по определению общих сценариев. Эти вопросы образуют платформу, не претендует на исчерпывающий характер, чтобы помочь товаров или услуг важные атрибуты своих сценариев.

### <a name="1-how-are-they-sharing"></a>1. Как они совместно используют?

Презентации может быть под руководством одного виртуального пользователя, хотя могут совместно работать несколько пользователей, или преподаватель может рекомендации виртуального учащимся, работа с материалами виртуального — сложность возрастает опыт основана на уровень агентства, у пользователя есть или можно использовать в сценарии.

![Мужчина и женщинами с holograph для таблицы](images/man-and-women-with-holograph-on-table-500px.png)

Существует много способов для совместного использования, но мы обнаружили, что большинство из них делятся на три категории:
* **Презентации**: Если нескольким пользователям отображается то же содержимое. Пример: Профессором раздавали лекция для нескольких студенты, использующие тот же holographic материал, представляемых для всех пользователей. Профессор тем не менее может иметь свои собственные советы и заметки, которые могут быть не видны другим пользователям.
* **Совместная работа**: Когда люди сотрудничают, чтобы достичь некоторых общих целей. Пример: Профессор присваивает проекта, чтобы узнать о выполнении хирургии. Учащиеся сопоставить и создайте практическому занятию общего навыки, позволяющий медицинских учащихся для совместной работы на основе модели и узнайте.
* **Руководство по**: Если один человек помогает кто-то, чтобы решить проблему в диалоге стиль более одной. Пример: Профессор, дам рекомендации для учащихся, когда он выполняет лаборатории навыки хирургии сердца в общий интерфейс.

### <a name="2-what-is-the-group-size"></a>2. Что такое размер группы?

**Один к одному** обмен впечатлениями может обеспечить надежный базовый и в идеале вашей экспериментов могут создаваться на этом уровне. Но имейте в виду, что совместное использование с больших групп (за пределами 6 людей) может привести к трудности из technical (данных и сети) в социальных сетях (влияние, в комнате с [несколько аватары](https://vimeo.com/160704056)). Сложность растет в геометрической прогрессии при переходе из **небольшой** для **больших групп**.

Мы пришли к выводу, что потребностей групп можно разделить на три категории размера:
* 1:1
* Небольшой < 7
* Большой > = 7

Размер группы делает для важный вопрос, так как оно влияет:
* Представления сотрудников в holographic пространства
* Масштабирование объектов
* Масштабирование среды

### <a name="3-where-is-everyone"></a>3. Где находится всем пользователям?

Интенсивность смешанной реальности вступает в действие, когда общий интерфейс может выполняться в том же расположении. Это называется **совместное размещение**. И наоборот когда группы распространяется, а также по крайней мере один из участников не находится в том же физическом пространстве (как это часто бывает в случае с VR) мы называем, удаленного взаимодействия. Часто бывает так, что в группе **оба** совместно размещенных данных и удаленных участников (например, две группы в конференц-залах).

![Три сотрудника с holograph для таблицы](images/three-people-with-holograph-on-table-500px.png)

Следующие категории помочь передачи, где находятся пользователи.
* Совместное размещение: Всем пользователям будет находиться в том же физическом пространстве.
* Удаленный: Все пользователи будут в отдельных физических пространствах.
* Оба: Пользователям будет сочетание совместно размещенных данных и удаленного пробелы.

Некоторые причины, почему этот вопрос имеет решающее значение, так как оно влияет:
* Способ взаимодействия людей?
* Пример: Ли они должны иметь аватары?
* Новые объекты, они видят. Все объекты являются общими?
* Необходимо ли адаптироваться к своей среде?

### <a name="4-when-are-they-sharing"></a>4. Когда они находятся?

Обычно бывает **синхронной** возникает, когда на ум приходит публикацию: Мы все делаем его друг с другом. Но включают один виртуальный элемент, который был добавлен другим пользователем, и у вас есть **асинхронной** сценария. Представьте себе, заметки или голосовое напоминание, оставить в виртуальной среде. Как обрабатывать 100 виртуального нот влево на разработке? Что делать, если они принадлежат десятки людей с разными уровнями конфиденциальности?

Рассмотрим своим опытом, как один из этих категорий времени:
* **Синхронно**: Совместное использование в голографический интерфейс, в то же время. Пример: Выполнение лаборатории навыки, в то же время работы двух учащихся.
* **Асинхронно**: Совместное использование в голографический интерфейс в разное время. Пример: Выполнение лаборатории навыки, но работает на работы двух учащихся отделить разделы в разное время.
* **Оба**: Пользователи иногда совместном использовании синхронно но в других случаях асинхронно. Пример: Профессор градации назначения, выполненных учащихся на более позднее время и оставляя примечания для учащегося за следующий день.

Некоторые причины, почему этот вопрос важно, так как ее влияние на:
* Сохраняемость объекта и среды. Пример: Сохранение состояния, поэтому они могут быть получены.
* Точки зрения пользователя. Пример: Возможно вспомнить, что пользователь смотрел при выходе из заметки.

### <a name="5-how-similar-are-their-physical-environments"></a>5. Насколько похожи их физических сред?

Вероятность двух идентичных сред реальной жизни за пределами совмещенной опыт, является упрощенной, если эти среды были разработаны как идентичные. Вы вероятно, что **аналогично** сред. Например, конференц-залы похожи — обычно требуется централизованное местоположение таблицы, заключенных в стульев. Гостиных, обычно с другой стороны, являются **разных форматов** и могут включать любое количество частей мебель бесконечный массив макетов.

![Holograph для таблицы](images/holograph-on-table-500px.png)

Рассмотрите возможность управления доступом опытом вмещаются в одно из этих двух категорий:
* **Аналогично**: Среды, которые часто имеют аналогичные мебель, внешнее освещение и звука, физический размер области колебания. Пример: Профессор является в лекции hall A и учащихся лекции hall лекции б hall объект может иметь стульев меньше, чем B, но они оба могут иметь физической службы поддержки снабдить голограммы.
* **Разнородные**: Среды, в которых есть довольно большие различия в параметры мебель, размеры комнаты, вопросы света и звука. Пример: Профессор состоит в помещении фокуса, тогда как учащихся находятся в крупных лекции hall, заполненный студентов и преподавателей.

Очень важно думать о среде, так как оно влияет на:
* Как пользователи будут испытывать эти объекты. Пример: Если процесс лучше всего работает в таблице, и у пользователя нет таблицы? Или на рабочую область неструктурированный floor, но пользователь имеет загроможденной пробел.
* Масштаб объектов. Пример: Размещение модель 6 футов человека в таблице может оказаться сложной задачей, но модель сердце будет прекрасно работать.

### <a name="6-what-devices-are-they-using"></a>6. Какие устройства используют ли они?

Сегодня вы часто встречаются общие ассоциации между двумя **иммерсивных устройств** (эти устройства могут немного отличаться с точки зрения кнопки и возможность относительного, но существенно не) или два **holographic устройств** учитывая решений предназначенных для этих устройств. Но Обратите внимание на **2D устройств** (участник мобильного или рабочего стола или наблюдателя) будет необходимо учитывать, особенно в случаях, если **смешанный 2D и 3D устройств**. Типы устройств, которую будете использовать участников важно понимать, не только в том случае, поскольку они поставляются с разных точности и ограничений данных и возможности, но так как у пользователей имеются различные уникальный для каждой платформы.

## <a name="exploring-the-potential-of-shared-experiences"></a>Изучение возможностей публикацию

Чтобы лучше понять сценарии общего, crystallizing трудности, так как дополнять этот интерфейс можно объединить ответы на вопросы выше. В группе корпорации Microsoft это помогло установить план развития по улучшению опыта мы используем сегодня, основные сведения о nuance этих сложных проблем и способов воспользоваться преимуществами публикацию в смешанной реальности.

Например, рассмотрим один из сценариев Скайп от запуска HoloLens: пользователь работал через [способы устранения неработающих выключатель света](https://www.youtube.com/watch?v=iBfzs3G8BEA) с помощь от экспертов, удаленно расположенных.

![Исправление выключатель света с помощью помощи через Скайп для HoloLens](images/fix-a-broken-switch-with-hololens-640px.jpg)

<i>Эксперт предоставляет <b>1:1</b> рекомендации из его <b>2D</b>, настольный компьютер, чтобы пользователь <b>3D, смешанной реальности</b> устройства. <b>Рекомендации</b> — <b>синхронной</b> и физических окружений <b>разных форматов</b>.</i>

Интерфейс следующим образом — это шаг изменение из текущего опыта — применение парадигму звука и видео в новой среде. Однако поскольку мы смотрим в будущее, мы должны лучше определить возможности сценариев и организовать взаимодействие с пользователями, которые отражают интенсивность смешанной реальности.

Рассмотрите возможность [средство совместной работы OnSight](https://www.youtube.com/watch?v=ZOWQp0-Bkkw) разработанный ракетных NASA. Работа с данными из миссию марсохода Mars по обработке и анализу могут работать совместно с коллегами в режиме реального времени в данных из Martian альбомной ориентации.

![Совместная работа между коллегами запятыми удаленно планирования работы для Rover режима Mars](images/onsight-nasa-jpl.gif)

<i>Специалист по обработке исследует среду с помощью <b>3D, смешанной реальности</b> устройства с помощью <b>небольшой</b> группе <b>удаленного</b> коллегами с помощью <b>двухмерной и трехмерной графики</b> устройства. <b>Совместной работы</b> — <b>синхронной</b> (но можно пересматривать асинхронно) и физической среды — это (буквально) <b>аналогично</b>.</i>

Функциональные возможности, например OnSight представляют новые возможности для совместной работы. Из физически акцентирование элементов в виртуальной среде, стоящий рядом с коллегами и общий доступ к их точки зрения представят результатами своей работы. OnSight использует линз общения, а также наличие пересмотреть возможности общего доступа в смешанной реальности.

Интуитивно понятный совместной работы является фундаментом диалог "и" Совместная работа и основные сведения о том, как можно применить этот интуиция сложности смешанной реальности имеет решающее значение. Если мы можно не только воссоздать возможности общего доступа в смешанной реальности, но расширение возможностей их, он будет парадигмы для будущей работы. Разработка для общего опыта при работе в смешанной реальности — новые и интересные места — и мы можем только в начале.

## <a name="get-started-sharing-experiences"></a>Начало работы обмен впечатлениями

В зависимости от приложения и сценарии будет различным требованиям для достижения требуемой работы. Ниже перечислены некоторые из них
* Обеспечение соответствия: Возможность создавать сеансы, объявить сеанс и обнаружить и Пригласите конкретные пользователи, и локально и удаленно подключиться к сеансу.
* Привязка совместного использования: Возможность выровнять координаты на различных устройствах в распространенных локального пространства, поэтому голограммы отображаются в одном расположении для всех пользователей.
* Сетевые подключения: Помещает возможность взаимодействия, и перемещений людей и голограммы синхронизируются в режиме реального времени для всех участников.
* Сохранение состояния: Возможность хранения характеристики голограмма и расположений в пространстве для присоединения к середине сеанса, помните, в более поздней версии время и надежность сетевых проблем.


Публикацию лежат несколько пользователей, видеть же голограммы в мире на свое собственное устройство, часто используется путем совместного использования привязки для выравнивания координаты на устройствах.
Чтобы предоставить общий доступ привязки, используйте <a href="https://docs.microsoft.com/azure/spatial-anchors" target="_blank">привязки пространственных Azure</a>:
* Сначала пользователь помещает голограмма.
* Приложение создает [пространственных привязки](coordinate-systems.md) для закрепления этого голограмма точно в мире.
* Привязки может использоваться для HoloLens, устройств iOS и Android с помощью <a href="https://docs.microsoft.com/azure/spatial-anchors" target="_blank">привязки пространственных Azure</a>. 

С помощью общего пространственных привязки приложения на каждом устройстве теперь имеет общую систему координат, в котором можно разместить содержимое. Теперь приложение можно обеспечить для размещения и ориентация голограмма в одном месте.
На устройствах, HoloLens вы можете поделиться привязки автономно с одного устройства на другой.  Используйте ссылки ниже для определения наиболее подходящего для вашего приложения.


## <a name="see-also"></a>См. также
* <a href="https://docs.microsoft.com/azure/spatial-anchors" target="_blank">Azure пространственных привязки</a>
* [Общие пространственных привязки в DirectX](shared-spatial-anchors-in-directx.md)
* [Публикацию в Unity](shared-experiences-in-unity.md)
* [Представление spectator](spectator-view.md)