---
title: Заметки о выпуске — октября 2018 г.
description: HoloLens и заметки о выпуске Windows Mixed Reality для Windows 10 октября 2018 года обновления (также известный как RS5).
author: mattzmsft
ms.author: mazeller
ms.date: 10/02/2018
ms.topic: article
keywords: Release notes, версии, windows 10, сборки, rs5, операционной системы
ms.openlocfilehash: 9838b4dcbdedc4bf2c94a8e31f3f8eb4c9634d36
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59604160"
---
# <a name="release-notes---october-2018"></a>Заметки о выпуске — октября 2018 г.

**[Обновления Windows 10 октября 2018 года](https://blogs.windows.com/windowsexperience/2018/10/02/find-out-whats-new-in-windows-and-office-in-october/)** (также известный как RS5) содержит новые функции для HoloLens и Windows Mixed Reality иммерсивную, подключенных к ПК. 

Чтобы обновить до последней версии на HoloLens или ПК (для Windows Mixed Reality иммерсивную (VR)), откройте **параметры** приложение, перейдите к **обновление и безопасность**, а затем выберите **поиск обновления** кнопки. На ПК с Windows 10, можно также вручную установить Windows 10 октября 2018 г. обновление с помощью [средство создания Windows media](https://www.microsoft.com/software-download/windows10).

**Последний выпуск для рабочего стола:** Центр обновления Windows 10 октября 2018 года (**10.0.17763.107**)<br>
**Последний выпуск для HoloLens:** Центр обновления Windows 10 октября 2018 года (**10.0.17763.134**)<br>

## <a name="new-features-for-windows-mixed-reality-immersive-headsets"></a>Новые возможности Windows Mixed Reality иммерсивную

Windows 10 октября 2018 обновление включает в себя множество улучшений по использованию Windows Mixed Reality иммерсивную (VR) с настольного компьютера.

### <a name="for-everyone"></a>Для всех пользователей

* **Смешанный фонариком реальность** : откройте портал в реальном мире, чтобы найти клавиатуры, см. в разделе, кто-то поблизости или взгляните на своем без удаления вашей гарнитура! Вы можете включить фонариком смешанной реальности из меню «Пуск», нажав клавиши Windows + захвата на контроллере движения, или произнести «Фонариком on/off». Точки контроллера в направлении, что вы хотите увидеть, как использовать фонарик в темноте.

    ![Фонариком смешанной реальности](images/mr-flashlight.png)

* **Новые приложения и способов запуска содержимого в смешанной реальности home**
    * Если вы используете [Windows Mixed Reality для SteamVR](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/using-steamvr-with-windows-mixed-reality), свои заголовки SteamVR теперь отображаются в меню "Пуск" и средствах запуска приложений для каждого может размещаться в смешанной реальности home.
    
        ![SteamVR средствах запуска приложений](images/steamvr-launchers.png)
        
    * Новый *360 видео* приложения для обнаружения регулярно проверенный подборку видео 360 градусов.
    * Новый *WebVR Showcase* работа приложения для обнаружения регулярно проверенный набор WebVR.
    * Клиенты Windows Mixed Reality первый раз будет введите со скалы дома и найти его предварительно заполненные в средствах запуска приложений 3D для некоторые из наших любимых мощных приложений и игр из Microsoft Store.
    * Microsoft Edge windows теперь включают *общего ресурса* кнопки.
* **Меню быстрых действий** -из в приложения впечатляющие смешанной реальности, можно нажать кнопку Windows для доступа к меню быстрых действий, новый, удобный доступ к *меню SteamVR*, *захват фото или видео*, *фонариком*, и *домашней*.
* **Поддержка рюкзаке ПК** -Windows Mixed Reality иммерсивную (VR) работу на рюкзаке ПК без эмулятор дисплея, после завершения установки.
* **Новые возможности аудио** -теперь предусмотрено аудио в интерфейсе Windows Mixed Reality как аудио Джек (или наушники) в вашей гарнитура *и* аудиоустройств, подключенном к ПК (например, внешние динамики). Мы также добавили визуальный индикатор для корпоративного уровня в вашей гарнитура отображения.
* **Другие усовершенствования**
    * Смешанной реальности портала обновлений теперь предоставляется через Microsoft Store, включение быстрое обновление между основными выпусками Windows. Обратите внимание, что это относится только к классическое приложение и удобство гарнитуры смешанной реальности Windows по-прежнему обновляет с операционной Системой. 
    * При гарнитуры переходят в спящий режим, приложения Windows Mixed Reality приостанавливаются вместо завершен (до закрытия смешанной реальности портала).
    
### <a name="for-developers"></a>Для разработчиков

* **[QR-код отслеживания](qr-code-tracking.md)**  -включить QR-кода, отслеживания в приложении смешанной реальности, позволяя Windows Mixed Reality (VR) иммерсивную для обнаружения QR-коды и сообщать их обратно в заинтересованы приложений.
* **Поддержка оборудования DRM для иммерсивных приложений** -разработчики могут теперь запрос защищенного оборудования буфера фона текстуры, если поддерживается оборудования, что позволяет приложениям использовать содержимое с защищенными оборудования из источников, например PlayReady.
* **[Интеграция отслеживания смешанной реальности пользовательского интерфейса в мощных приложений на](mixed-reality-capture-for-developers.md#integrating-mrc-functionality-from-within-your-app)**  -разработчики могут интегрировать смешанной реальности захвата в свои приложения с помощью встроенных Windows [пользовательский Интерфейс камеры](https://docs.microsoft.com/windows/uwp/audio-video-camera/capture-photos-and-video-with-cameracaptureui) с помощью всего нескольких строк кода.

## <a name="new-features-for-hololens"></a>Новые возможности для HoloLens

Windows 10 октября 2018 Update является общедоступным для всех клиентов HoloLens и включает в себя ряд улучшений, таких как:

### <a name="for-everyone"></a>Для всех пользователей

* **Меню быстрых действий** -из в приложения впечатляющие смешанной реальности, можно нажать кнопку Windows для доступа к меню быстрых действий, новый, удобный доступ к *начать запись видео*, *сфотографировать*, *Mixed реальности домашней*, *изменение громкости*, и *Connect*.
* **Запуск и остановка видеозаписи с начала или с меню быстрых действий** -Если видеозаписи запускается из меню "Пуск" или меню быстрых действий, вы сможете остановить запись в одном месте. (Не забывайте, всегда это можно сделать с помощью голосовых команд слишком.)
* **Проект для устройства, поддерживающего технологию Miracast** -проект содержимого HoloLens поблизости устройств Surface или Телевизор или монитор, при использовании поддерживающего технологию Miracast экрана или адаптера.
* **Уведомления о новых** -представление и реагирование на уведомления о HoloLens, так же, как на ПК.  
* **Полезные перекрытия в приложения впечатляющие смешанной реальности** -теперь отображается наложения, таких как клавиатура, диалоговые окна, средство выбора файлов, и т.д., при использовании иммерсивных приложениях смешанной реальности.
* **Визуальный индикатор для изменения объема** — при использования тома / вниз на вашей HoloLens вы увидите визуальным индикатором уровень громкости в гарнитуры.
* **Новые визуальные элементы для загрузки устройства** -Признак загрузки был добавлен во время загрузки для предоставления визуальной обратной связи, в которой система загружается.
* **Под рукой совместное использование** -Windows рядом совместное использование работы позволяет совместно использовать записи с близлежащими устройствами Windows.  
* **Общий ресурс из браузера Microsoft Edge** -теперь включает Microsoft Edge *общего ресурса* кнопки. 

### <a name="for-developers"></a>Для разработчиков

* **[Интеграция отслеживания смешанной реальности пользовательского интерфейса в мощных приложений на](mixed-reality-capture-for-developers.md#integrating-mrc-functionality-from-within-your-app)**  -разработчики могут интегрировать смешанной реальности захвата в свои приложения с помощью встроенных Windows [пользовательский Интерфейс камеры](https://docs.microsoft.com/windows/uwp/audio-video-camera/capture-photos-and-video-with-cameracaptureui) с помощью всего нескольких строк кода.

### <a name="for-commercial-customers"></a>Для коммерческих клиентов

* **Включить подготовку после установки** -теперь можно применить пакет подготовки в любое время с помощью параметров среды выполнения.
* **Назначен доступ с помощью групп Azure AD** -теперь можно использовать группы Azure AD для настройки Windows, назначен доступ для настройки конфигурации киоска одним или с несколькими приложениями.
* **ЗАКРЕПИТЬ входа в систему на коммутаторе профиль с экрана входа в систему** -вход ПИН-код теперь доступен для «Другой пользователь» на экране входа в систему. 
* **Войдите с помощью поставщике учетных данных с использованием пароля** — теперь вы можете выбрать значок глобуса для запуска в веб-входа с паролем. 
* **Чтение сведений об оборудовании устройства через MDM** -ИТ-администраторы могут см. в разделе и отслеживать HoloLens с серийный номер устройства в консоли управления мобильными Устройствами.
* **Задайте имя устройства HoloLens через MDM (переименовать)** -ИТ-администраторы могут см. в разделе и переименовывать HoloLens устройств в консоли управления мобильными Устройствами.

### <a name="for-international-customers"></a>Для международных заказчиков

Теперь можно использовать HoloLens с локализованным пользовательским интерфейсом для китайского языка с упрощенным или японском языке, включая локализованной клавиатуре ПИН-инь, диктовки, преобразования текста в речь (TTS) и голосовые команды.

## <a name="known-issues"></a>Известные проблемы

Мы сделали все возможное для доставки удобной Windows Mixed Reality, но мы по-прежнему отслеживаются некоторые известные проблемы. Если вы найдете другие, [отзыв](https://docs.microsoft.com/windows/mixed-reality/give-us-feedback).

### <a name="hololens"></a>HoloLens
 
#### <a name="after-update"></a>После обновления
При использование Windows 10 октября 2018 Update на вашей HoloLens, могут возникать следующие проблемы:
* **Приложения могут оказаться в входа в цикл, при запуске для уведомления** — некоторые приложения, требующие входа в систему можно получить в бесконечном входа в цикле при запуске для уведомления. Например это может произойти после установки приложения корпоративного портала Microsoft из Microsoft Store и запустив его из уведомление о завершении установки.
* **Страница входа в приложения можно выполнить с пустой страницы** — в некоторых случаях, когда отображается входа в систему через приложение, по завершении страницы входа не закрывается и вместо этого отображает пустую страницу (черный). Можно закрыть пустую страницу или переместите его для анализа данных в приложение в пределах. Например это может произойти при входе во время регистрации MDM из приложения параметров. 

## <a name="provide-feedback-and-report-issues"></a>Предоставить отзыв или сообщить о проблеме

Используйте [приложение центр отзывов на ПК с Windows 10 или HoloLens](give-us-feedback.md) для предоставления отзыв или сообщить о проблеме. С помощью центра обратной связи обеспечивает все необходимые диагностические данные для упрощения наши инженеры быстро отладки и устранения проблемы.

>[!NOTE]
>Не забудьте принять приглашение, которое запрашивает, нужна ли центр отзывов на доступ к папке документы (выберите **Да** при появлении запроса).

## <a name="prior-release-notes"></a>Заметки о выпуске для предыдущих

* [Заметки о выпуске — апрель 2018 г.](release-notes-april-2018.md)
* [Заметки о выпуске — октябрь 2017 г.](release-notes-october-2017.md)
* [Заметки о выпуске — август 2016 г.](release-notes-august-2016.md)
* [Заметки о выпуске — май 2016 г.](release-notes-may-2016.md)
* [Заметки о выпуске — март 2016 г.](release-notes-march-2016.md)

## <a name="see-also"></a>См. также
* [Поддержка иммерсивных Гарнитура (внешняя ссылка)](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/troubleshooting-windows-mixed-reality)
* [Поддержка HoloLens (внешняя ссылка)](https://support.microsoft.com/products/hololens)
* [Установка средств](install-the-tools.md)
* [Отзыв о нас](give-us-feedback.md)

