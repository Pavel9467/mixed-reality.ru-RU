---
title: Заметки о выпуске — октябрь 2017 г.
description: Заметки о выпуске Windows Mixed Reality для Windows 10 Fall Creators Update (октябрь 2017 г.).
author: mattzmsft
ms.author: mazeller
ms.date: 03/21/2018
ms.topic: article
keywords: Release notes, версии, windows 10, сборки, rs3, операционной системы
ms.openlocfilehash: 7274dcf1db449fa35981eb72192fea9873fcc90a
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59597829"
---
# <a name="release-notes---october-2017"></a>Заметки о выпуске — октябрь 2017 г.

Добро пожаловать в смешанной реальности Windows! В выпуске **[Windows 10 Fall Creators Update](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update/)** появилась поддержка для новых [Windows Mixed Reality иммерсивную](immersive-headset-hardware-details.md) и [движения контроллеров ](motion-controllers.md), что позволяет исследовать новые миры, VR играть и возникнуть мир развлечений, при подключении к [capable PC Windows Mixed Reality](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/windows-mixed-reality-minimum-pc-hardware-compatibility-guidelines).

Выпуск гарнитуры смешанной реальности Windows и контроллеров движения является кульминацией значительных усилий и это большой шаг вперед для [платформы Windows Mixed Reality](mixed-reality.md), который включает [Microsoft HoloLens](hololens-hardware-details.md). Хотя HoloLens не получает обновления с выпуском Windows 10 Fall Creators Update, знаете, что работа над HoloLens не помешало; у нас будет много знания и понимание применить из наших недавней работе Windows Mixed Reality в целом. На самом деле, Windows Mixed Reality иммерсивную и движения контроллеры представлять запись отличный точкой к разработке для HoloLens слишком те же интерфейсы API, средства, и концепции применяются к обеим версиям.

Чтобы обновить до последней версии для каждого устройства, откройте **параметры** приложение, перейдите к **обновление и безопасность**, а затем выберите **проверять наличие обновлений** кнопки. На ПК с Windows 10, можно также вручную установить в Windows 10 Fall Creators Update с помощью [средство создания Windows media](https://www.microsoft.com/software-download/windows10).

 **Последний выпуск для рабочего стола:** Рабочий стол Windows 10 октября 2017 г. (**10.0.16299.15**, Windows 10 Fall Creators Update)<br>
 **Последний выпуск для HoloLens:** [Windows 10 Holographic август 2016 г.](release-notes-august-2016.md) (**10.0.14393.0**, Юбилейное обновление Windows 10)

>[!VIDEO https://www.youtube.com/embed/YBcLy1lkegg]

## <a name="introducing-windows-mixed-reality"></a>Знакомство с Windows Mixed Reality

Windows 10 Fall Creators Update официально добавлена поддержка гарнитуры смешанной реальности Windows и контроллеров движения, а также сделать в мире первый пространственных операционной системой Windows 10. Ниже приведены ключевые элементы.
* **[Различные гарнитуры](https://blogs.windows.com/windowsexperience/2017/10/03/how-to-pre-order-your-windows-mixed-reality-headset/)**  -смешанной реальности Windows используется, чтобы предоставить партнерам предлагают различные гарнитуры, какие start в 399 Долларов США в состав контроллеры движения.
* **[Движения контроллеров](motion-controllers.md)**  -контроллеров движения Windows Mixed Reality через беспроводное соединение связываться с персональным Компьютером через Bluetooth и признаков шесть степеней свободы отслеживания, множество IMUs и методы ввода.
* **[Простая настройка и переносимость](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/recommended-adapters-for-windows-mixed-reality-capable-pcs)**  — переводит вверх и начать работу в течение 10 минут. Иммерсивную используйте внутренний отслеживания для отслеживания вашего перемещения и контроллерах движения с шесть степеней свободы. Нет внешних камеры или свету маркеров требуется!
* **[Поддержка широкого диапазона ПК](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/windows-mixed-reality-minimum-pc-hardware-compatibility-guidelines)**  -Windows Mixed Reality позволит больше людей могло возникнуть рабочего стола виртуальной Реальности, чем когда-либо, с поддержкой выберите интегрировать графические платы и ПК, начиная с 499 Долларов США.
* **[Windows Mixed Reality домашней](navigating-the-windows-mixed-reality-home.md)**  -в мире первый пространственных операционная система предоставляет знакомую среду домашней для многозадачных с 2D приложений, запускающий VR игр и приложений и размещение декоративных голограммы.
* **[Удивительно VR игр и приложений в Microsoft Store](https://www.microsoft.com/store/collections/MR-All-ImmersiveContent/)**  : от мир развлечений, как Hulu виртуальной Реальности и 360 видео эпические игры, такие как SUPERHOT виртуальной Реальности и Солнца Аризона, Microsoft Store имеет диапазон содержимого, которое вы можете работать в смешанном Windows Реальность.
* **[Ранний доступ SteamVR](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/using-steamvr-with-windows-mixed-reality)**  — Windows 10 Fall Creators Update включает поддержку SteamVR заголовки для воспроизведения с гарнитуры смешанной реальности Windows и контроллеров, делая наибольшее каталог VR наименования доступными для смешанных Windows Пользователи, реальность.

## <a name="known-issues"></a>Известные проблемы

Мы сделали все возможное для доставки удобной Windows Mixed Reality, но мы по-прежнему отслеживаются некоторые известные проблемы. Если вы найдете другие, [отзыв](give-us-feedback.md).

### <a name="desktop-app-in-the-windows-mixed-reality-home"></a>Классическое приложение в Windows Mixed Reality home
* Ножницы не работает в настольном приложении.
* Классическое приложение не сохраняет параметр при повторном запуске.
* При использовании смешанной реальности портала предварительной версии на рабочем столе, при открытии классического приложения в Windows Mixed Reality home, вы можете заметить влияние бесконечный зеркальной. 
* Запуск классического приложения могут вызвать проблемы производительности на не - Ultra смешанной реальности компьютеров под управлением Windows; не рекомендуется.  
* Классическое приложение может автоматически запускать так, как невидимый окно на рабочем столе имеет фокус. 
* Настольных систем контроля учетных записей строке сделает гарнитура отображения черный, пока завершится в командной строке.

### <a name="windows-mixed-reality-setup"></a>Программа установки Windows Mixed Reality
* При настройке Windows с помощью подключение гарнитуры, монитор ПК могут отключаться. Отключите вашей гарнитуры, чтобы включить вывод на монитор компьютера для завершения установки Windows.
* При создании границы, трассировка может завершиться ошибкой. Если это так, повторите попытку, как система будет рассказано о своем пространстве со временем.
* Если Cortana или отключить во время установки Windows Mixed Reality, это изменение будет применено ко параметры рабочего стола Cortana.
* Если у вас наушники, можно пропустить Дополнительные советы при первом посещении Windows Mixed Reality home.
* Наушники Bluetooth могут создавать помехи с контроллерами движения. Мы рекомендуем разрыв соединения или выключения Bluetooth контроллеров во время сеансов Windows смешанной реальности.

### <a name="games-and-apps-from-windows-store"></a>Игры и приложения из Windows Store
* Некоторые насыщенных графикой игры, например Forza Motorsports 6, может вызвать снижение производительности на менее эффективном ПК при воспроизведении в Windows Mixed Reality.

### <a name="audio"></a>Звук
* Как отмечалось выше, периферийные устройства Bluetooth аудио не работают с Windows Mixed Reality голосовой и пространственных звуковые возможности. Они могут также отрицательно повлиять на работу контроллера движения. Не рекомендуется использовать Bluetooth аудио гарнитуры со смешанной реальностью Windows.
* Нельзя использовать звуковые устройства, подключенного к (или частично) гарнитура для воспроизведения звука, когда устройство не надет. При наличии только одного головные, можно подключиться к узлу ПК вместо гарнитура головные. Если таким образом, затем необходимо отключить параметр «переключиться на аудио гарнитура» **параметры** > **смешанной реальности** > **аудио- и речи**.
* Некоторые приложения, включая многих из них запускаются через SteamVR, можно потерять аудио или зависанию при изменении звуковое устройство при запуске или остановке портале смешанной реальности. После открытия приложения смешанной реальности портала, чтобы устранить эту проблему, перезапустите приложение.
* Если у вас включена на узле ПК до использования вашей гарнитуры смешанной реальности Windows Кортана, можно потерять пространственных звуковой моделирования, которые применяются к приложениям, что вы помещаете вокруг Windows Mixed Reality домашней. Решением проблемы является включение «Windows Sonic для наушников» на всех звуковых устройств, присоединенных к Компьютеру, даже подключение гарнитуры звуковое устройство:
   1. Щелкните левой кнопкой мыши значок динамика на панели задач рабочего стола и выберите из списка, звуковых устройств.
   2. Щелкните правой кнопкой мыши значок динамика на панели задач рабочего стола и выберите «Windows Sonic для наушников» в меню «Динамиков».
   3. Повторите эти шаги для всех устройств аудио (конечные точки).
>[!NOTE]
> - Так как наушники и динамиков, подключенных к вашей гарнитура не отображается, если вы носки, необходимо это сделать в окне приложения на рабочем столе в Windows Mixed Reality домашней Чтобы применить этот параметр для звукового устройства подключены к вашей Гарнитура (или интегрированный в вашей гарнитуры).
> - Другим вариантом является отключение «Let Cortana реагирование на Привет, Кортана!» в **параметры** > **Cortana** на рабочем столе до запуска Windows смешанной реальности.

* Когда другого мультимедийные устройства USB (например, веб-камера) использует один и тот же центр USB (внешним или внутри ПК) совместно с гарнитуры смешанной реальности Windows, в редких случаях гарнитура Джек/подключения наушников может либо вообще слышан звука или не содержат звука. Это можно исправить, ваш гарнитуры, USB-порту, который не совместно используют один и тот же центр как другое устройство или отключиться или отключить другие мультимедийные устройства USB.
* В очень редких случаях USB-концентратор узла компьютера не может предоставить достаточно возможностей, чтобы гарнитуры смешанной реальности Windows и вы можете заметить в пакетном режиме помех от наушники, подключенных к гарнитуры.

### <a name="speech"></a>Голосовые функции
* Cortana может завершиться ошибкой для воспроизведения ее аудиоподсказок для прослушивания/мышление и аудио отвечает на команды.
* Кортана на рынках, Китая и Японии больше не показывать правильно текст под элемент управления circle Cortana во время использования.
* Cortana может быть медленным в первый раз она вызывается в сеансе смешанной реальности портала. Это можно обойти, сделав действительно «Let Cortana реагировать на них Привет, Кортана!» в разделе **параметры** > **Cortana** > **взаимодействовать с Cortana** — включено.
* На компьютерах, которые не являются ПК Windows Mixed Reality Ultra Cortana может выполняться медленнее.
* Если система клавиатуры присвоено языке, отличном от языка пользовательского интерфейса в Windows Mixed Reality, с помощью режима диктовки с помощью клавиатуры в Windows Mixed Reality приведет к окно сообщения об ошибке о диктовки, не работает из-за отсутствия подключения Wi-Fi. Чтобы устранить проблему просто убедитесь, что системный язык клавиатуры соответствует языку пользовательского интерфейса Windows смешанной реальности.
* Испания правильно распознается как рынка, где поддержкой речевых функций для смешанной реальности Windows.

### <a name="holograms"></a>Голограммы
* Если большое количество голограммы поместили в вашей Windows Mixed Reality home, некоторые исчезают и снова при рассмотрении возможности. Чтобы избежать этого, удалите некоторые голограммы в этой области Windows Mixed Reality home.

### <a name="motion-controllers"></a>Контроллеры движения
* Иногда Если щелкнуть веб-страницы в браузере Microsoft Edge, содержимое будет масштаб вместо щелкните.
* Иногда в том случае, если щелкнуть ссылку в Microsoft Edge, выделение не будет работать.

## <a name="prior-release-notes"></a>Заметки о выпуске для предыдущих
* [Заметки о выпуске — август 2016 г.](release-notes-august-2016.md)
* [Заметки о выпуске — май 2016 г.](release-notes-may-2016.md)
* [Заметки о выпуске — март 2016 г.](release-notes-march-2016.md)

## <a name="see-also"></a>См. также
* [Поддержка иммерсивных Гарнитура (внешняя ссылка)](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/troubleshooting-windows-mixed-reality)
* [Известные проблемы HoloLens](hololens-known-issues.md)
* [Установка средств](install-the-tools.md)
* [Отзыв о нас](give-us-feedback.md)
