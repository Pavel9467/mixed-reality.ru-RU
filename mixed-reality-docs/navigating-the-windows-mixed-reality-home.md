---
title: Перемещение Windows Mixed Reality home
description: HoloLens и Windows Mixed Reality гарнитуры совместно использовать парадигму для запуска, размещения и использования приложений и трехмерными моделями в среде (независимо от физического или цифровой). Вы научитесь навигации Windows Mixed Reality, на обоих типов устройств.
author: mattzmsft
ms.author: mazeller
ms.date: 03/21/2018
ms.topic: article
keywords: оболочки, ОС, платформы, Александр дом, дома, home, среды, начало, меню "Пуск", домашней меню, ПИН-кодов, приложения, запуске приложений, поместите приложений, teleport, перемещать, перейдите
ms.openlocfilehash: 1ca6dd66506a64ad2e1c21870fee2725ddf20bd8
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59604896"
---
# <a name="navigating-the-windows-mixed-reality-home"></a>Перемещение Windows Mixed Reality home

Так же, как запуске планшетными ПК Windows с рабочим столом Windows Mixed Reality начинается с дома. Windows Mixed Reality домашней использует наши система дает возможность понять и перейти 3D местах. С HoloLens готова в физическом пространстве. С помощью иммерсивную домашней сети — это виртуальный место.

Также является домашней сети где меню "Пуск" будет использоваться для открытия и разместить приложения и содержимого. Можно заполнить дома содержимым смешанной реальности и справляется с помощью нескольких приложений одновременно. То, что вы помещаете домашней сети остаются там, даже при перезагрузке устройства.

## <a name="start-menu"></a>Меню "Пуск"

![Меню "Пуск" в Microsoft HoloLens](images/start-500px.png)

Меню "Пуск" состоит из:
* Сведения о системе (состояние сети, процент аккумулятора, текущее время и тома)
* Cortana (на иммерсивную плитки начала; HoloLens, в верхней части начала)
* Закрепленные приложения
* «Все» для приложений (плюс)
* Фото и видео в кнопки для [смешанный захвата реальность](mixed-reality-capture.md)

Переключаться между закрепленные приложения и все приложения, представления, выбрав значок плюс или минус. Чтобы открыть меню "Пуск" HoloLens, используйте жест раскрытия. В иммерсивной гарнитура нажмите кнопку Windows на контроллере.

## <a name="launching-apps"></a>Запуск приложений

Чтобы запустить приложение, выберите ее при запуске. Меню "Пуск" исчезнут, и приложение будет открываться в режиме размещения, как двумерный окна или [трехмерной модели](implementing-3d-app-launchers.md).

Чтобы запустить приложение, необходимо поместить в домашней сети:
1. Используйте ваши [помощи](gaze.md) или контроллеру для размещения приложения, где вам удобно. (В размер и положение) будет автоматически адаптирован в соответствии с места, где следует поместить.
2. Установите приложение с помощью касания воздуха (HoloLens) или кнопки "выбрать" (иммерсивную). Чтобы отменить и вернуть меню "Пуск", используйте жест раскрытия или кнопки Windows.

[2D приложений](building-2d-apps.md), созданный для классических, мобильных или Xbox можно изменить для выполнения в качестве смешанной реальности мощных приложений с помощью [HolographicSpace API](https://msdn.microsoft.com/library/windows/apps/windows.graphics.holographic.holographicspace.aspx). Насыщенные приложения открывалась из дома и поместить в присутствия. Пользователи могут вернуться на домашнюю страницу с данным жестом bloom (HoloLens), или нажатием кнопки «Windows» на свой контроллер (иммерсивную).

Приложения также могут запускаться через API-Интерфейс приложения в приложение или через Cortana.

![Приложения в Windows Mixed Reality home](images/mixed-reality-home-500px.png)

## <a name="moving-and-adjusting-apps"></a>Перемещение и настройка приложений

Выберите **Adjust** в приложении панели, чтобы показать элементы управления, перемещения, масштабирования, и поворот смешанное содержимое реальностью. Когда вы закончите, выберите **сделать**.

![Содержание рекламы хранилища, в режиме коррекции (синий кадр). Обратите внимание на панель приложения (верхнего) было изменено на «Готово» и «Удалить» кнопок.](images/adjust-500px.png)

Различные приложения может иметь дополнительные параметры на панели приложения. Например, Microsoft Edge имеет *прокрутки*, *перетащите*, и *масштаб* вариантов. 

![Панели приложения для 2D приложений, запущенных в HoloLens](images/holobar-500px.png)

**Обратно** кнопку переходит обратно в ранее просмотренного экранов в приложении. Останавливается, Дойдя до начала действия, которые отображаются в приложении и не будет перемещаться в другие приложения.

## <a name="getting-around-your-home"></a>Начало месте вашего дома

С помощью **HoloLens**, при перемещении по физическое пространство для перемещения месте вашего дома.

С помощью **иммерсивную**, аналогичным образом можно начать работу и вручную в вашей playspace для перемещения в пределах аналогичные области в виртуальный мир. Для перемещения по расстояниях, вы можете использовать джойстик на вашем контроллере для практически «прохода», или можно использовать *teleportation* немедленно перейти расстояниях.

![Teleportation в Windows Mixed Reality home](images/teleportation-500px.png)

**Чтобы teleport:**
1. Подключите teleportation маркер.
   * С помощью [движения контроллеров](motion-controllers.md): джойстик вперед, удерживая ее в этой позиции.
   * С помощью контроллера Xbox: левый джойстик вперед, удерживая ее в этой позиции.
   * С помощью мыши: удерживая нажатой кнопку мыши щелкните правой кнопкой мыши (и используйте колесо прокрутки, чтобы вращать направление для лиц, когда вы teleport).
2. Поместите маркер, в которой вы хотите teleport.
   * С помощью [движения контроллеров](motion-controllers.md): наклон контроллера (на котором вы держите в руках джойстик вперед), чтобы переместить маркер.
   * С помощью контроллера Xbox: использовать ваш [помощи](gaze.md) переместить маркер.
   * С помощью мыши: переместить указатель мыши, чтобы переместить маркер.
3. Отпустите кнопку, чтобы teleport, где был помещен маркер.

**Чтобы практически «стека:»**
* С помощью [движения контроллеров](motion-controllers.md): щелкните вниз джойстик и удержание, а затем переместить джойстик в направлении, требуется «прохода».
* С помощью контроллера Xbox: щелкните вниз левый джойстик и удержание, а затем переместить джойстик в направлении, требуется «прохода».

## <a name="immersive-headset-input-support"></a>Поддержка ввода иммерсивных гарнитура

[Windows Mixed Reality иммерсивную](immersive-headset-hardware-details.md) поддерживает множество типов входных данных для перемещения по Windows Mixed Reality home. HoloLens не поддерживает аксессуаров входные данные для навигации, так как физического присутствия и см. в разделе среды. Однако выполняет HoloLens [наборов входных данных](hardware-accessories.md) для взаимодействия с приложениями.

### <a name="motion-controllers"></a>Контроллеры движения

Получения наилучших результатов Windows Mixed Reality будет с Windows Mixed Reality [движения контроллеров](motion-controllers.md) отслеживания 6 степеней свободы, поддержку, использование только датчиков в гарнитура - без внешних камеры или маркеры, которые требуется!

Команды навигации, ожидается в ближайшее время.

### <a name="gamepad"></a>Геймпад
* **Левый джойстик:**
  * Нажмите и удерживайте клавишу левый джойстик вперед, чтобы открыть [teleportation](navigating-the-windows-mixed-reality-home.md#getting-around-your-home) маркер.
  * Коснитесь джойстик, слева, справа, серверной части требуется переместиться влево, вправо или обратно с небольшими шагами.
  * Щелкните в левый джойстик и удержание, затем переместите джойстик в требуемом направлении [практически «прохода».](navigating-the-windows-mixed-reality-home.md#getting-around-your-home)
* Коснитесь **правой джойстик** поворачивать возникают на 45 градусов вправо или влево.
* Нажав клавишу **объект** кнопка выполняет инструкцию select и действует как [жест касания](gestures.md#air-tap) жест.
* Нажав клавишу **руководство** будет открыто окно [меню "Пуск"](navigating-the-windows-mixed-reality-home.md#start-menu) и действует как [Блума](gestures.md#bloom) жест.
* Нажав клавишу **триггеры левого и правого** позволяет можно увеличивать или уменьшать масштаб 2D взаимодействие с на домашней странице приложения на рабочем столе.

### <a name="keyboard-and-mouse"></a>Клавиатуры и мыши

**Примечание.** Используйте **клавиши Windows + Y** переключиться мыши между управление настольных ПК и Windows Mixed Reality домашней.

В Windows Mixed Reality home:
* Нажав клавишу **левой кнопкой мыши щелкните** кнопки мыши выполняет инструкцию select и действует как [жест касания](gestures.md#air-tap) жест.
* Удерживая **щелкните правой кнопкой мыши** появится кнопка мыши [teleportation](navigating-the-windows-mixed-reality-home.md#getting-around-your-home) маркер.
* Нажав клавишу **Windows** клавиши на клавиатуре можно открыть [меню "Пуск"](navigating-the-windows-mixed-reality-home.md#start-menu) и действует как [Блума](gestures.md#bloom) жест.
* При [gazing](gaze.md) в 2D классического приложения, вы можете **левой кнопкой мыши щелкните** для выбора, **щелкните правой кнопкой мыши** открыть контекстные меню, и использовать **колесо прокрутки** для прокрутки (так же как и на рабочем столе компьютера).

## <a name="cortana"></a>Кортана

[Cortana](voice-input.md#hey-cortana) является вашего личного помощника в Windows Mixed Reality, так же, как на ПК и телефона. HoloLens имеет встроенный микрофон, но иммерсивную может потребоваться дополнительное оборудование. Используйте Cortana для открытия приложений, перезапуск устройства, найти через Интернет вещей и многое другое. Разработчики также могут [интеграция Cortana](https://dev.windows.com/cortana) в свои визуальные элементы.

Голосовые команды также можно получить месте вашего дома. Например, наведите на кнопку (с помощью [помощи](gaze.md) или контроллером, в зависимости от устройства) и сказать: «Выбрать». Другие голосовые команды включают «Go home», «Больше», «меньшего размера,» «Закрыть» и «Сталкиваются me».

## <a name="store-settings-and-system-apps"></a>Приложения Store "," Параметры "и" системы

Windows Mixed Reality имеет ряд встроенных приложений, таких как:
* **Microsoft Store** для получения приложения и игры
* **Центр отзывов** отзывы о системе и системные приложения
* **Параметры** на настройку системных параметров ([том числе сеть](connecting-to-wi-fi-on-hololens.md) и обновлений системы)
* **Microsoft Edge** для просмотра веб-сайтов
* **Фотографии** для просматривайте и совместно используйте фотографии и видео
* **Калибровка** (HoloLens) для настройки возможности HoloLens текущему пользователю
* **Узнайте, жесты** (HoloLens) или **Узнайте смешанной реальности** (иммерсивную) Дополнительные сведения об использовании устройства
* **Средство просмотра трехмерной** для оформления свой мир с помощью содержимого смешанной реальности
* **Смешанный портала на самом деле** (локальная) для настройки и управления вашей иммерсивных гарнитуры и потоковой передачи динамический просмотр представления гарнитура другим пользователям.
* **Фильмах и Телепередачах** для просмотра 360 видео и последнюю фильмов и ТВ показывает
* **Cortana** все ваши виртуальные помощники необходима
* **Рабочий стол** (иммерсивную) для просмотра рабочего стола монитора в иммерсивных гарнитура
* **Обозреватель файлов** доступ к файлам и папки, находящиеся на устройстве

## <a name="see-also"></a>См. также
* [Представления приложения](app-views.md)
* [Контроллеры движения](motion-controllers.md)
* [Стандартные оборудования](hardware-accessories.md)
* [Соображения, касающиеся среды для HoloLens](environment-considerations-for-hololens.md)
* [Реализация средствах запуска приложений 3D](implementing-3d-app-launchers.md)
* [Создании трехмерных моделей для использования в домашних Windows Mixed Reality](creating-3d-models-for-use-in-the-windows-mixed-reality-home.md)
