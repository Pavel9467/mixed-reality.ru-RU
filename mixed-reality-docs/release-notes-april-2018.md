---
title: Заметки о выпуске — апрель 2018 г.
description: HoloLens и заметки о выпуске Windows Mixed Reality для Windows 10 апреля 2018 г. обновления (также известный как RS4).
author: mattzmsft
ms.author: mazeller
ms.date: 05/21/2018
ms.topic: article
keywords: Release notes, версии, windows 10, сборки, rs4, операционной системы
ms.openlocfilehash: 1fc1b43b0581234e835379fd553b78121108086e
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59600906"
---
# <a name="release-notes---april-2018"></a>Заметки о выпуске — апрель 2018 г.

**[Обновления Windows 10 апреля 2018 г.](https://blogs.windows.com/windowsexperience/2018/04/30/whats-new-in-the-windows-10-april-2018-update)** (также известный как RS4) содержит новые функции для HoloLens и Windows Mixed Reality иммерсивную, подключенных к ПК. 

Чтобы обновить до последней версии для каждого типа устройства, откройте **параметры** приложение, перейдите к **обновление и безопасность**, а затем выберите **проверять наличие обновлений** кнопки. На ПК с Windows 10, можно также вручную установить Windows 10 апреля 2018 г. обновление с помощью [средство создания Windows media](https://www.microsoft.com/software-download/windows10).

**Последний выпуск для рабочего стола:** Центр обновления Windows 10 апреля 2018 г. (**10.0.17134.1**)<br>
**Последний выпуск для HoloLens:** Центр обновления Windows 10 апреля 2018 г. (**10.0.17134.80**)<br>
<br>

>[!VIDEO https://www.youtube.com/embed/O-84oWjSbr0]

*Обновить сообщение от Алекс Ęčďěŕн и обзор новых возможностей смешанная реальность в Windows 10 апреля 2018 г.*

## <a name="new-features-for-windows-mixed-reality-immersive-headsets"></a>Новые возможности Windows Mixed Reality иммерсивную

Windows 10 апреля 2018 г. обновление включает в себя множество улучшений по использованию Windows Mixed Reality иммерсивную (VR) с настольного компьютера, такие как: 

* **Новые среды для смешанной реальности домашней** -теперь можно выбрать между со скалы дома и новой средой Skyloft, выбрав **местах** в меню "Пуск". Мы также добавили [экспериментальной функцией](add-custom-home-environments.md) , позволит вам использовать пользовательские среды, вы создали.
* **Быстрый доступ к записи смешанной реальности** -дают возможность смешанной реальности фотографий с помощью контроллера движения. Удерживайте кнопку Windows и выберите триггер. Это работает в средах и приложений, но не записывают содержимое, защищенное с помощью DRM.
* **Новые параметры для запуска и изменения размеров содержимого** -приложений автоматически размещаются перед глазами при запуске из меню "Пуск". Кроме того, теперь можно изменить размер 2D приложений путем перетаскивания границ и углов окна.
* **Легко переходить к содержимому с помощью голосовых команд «teleport»** — теперь вы можете быстро teleport быть перед содержимым в Windows Mixed Reality home, gazing на содержимое и сказать: «teleport.»
* **[Анимация средствах запуска приложений 3D](creating-3d-models-for-use-in-the-windows-mixed-reality-home.md#animation-guidelines) и [декоративных трехмерные объекты](enable-placement-of-3d-models-in-the-home.md) для смешанной реальности домашней** -теперь можно добавить анимации в средствах запуска приложений 3D и разрешить пользователям для размещения декоративного 3D-моделей из приложения веб-страницы или 2D в Windows Mixed Reality home.
* **[Улучшения в Windows Mixed Reality SteamVR](updating-your-steamvr-application-for-windows-mixed-reality.md)**  -Windows Mixed Reality для SteamVR выходит за пределы «ранний доступ», с помощью новых обновлений, включая: обратной связи haptic при использовании контроллеров движения, улучшенную производительность и надежность, и улучшения внешнего вида движения контроллеров в SteamVR.
* **Другие усовершенствования** -параметры автоматического производительности были обновлены для обеспечения более оптимизированного (вы можете [вручную переопределить](#visual-quality) этот параметр). Программа установки теперь предоставляет более подробные сведения о распространенных проблемах совместимости с помощью контроллеров и графических карт USB 3.0.

## <a name="new-features-for-hololens"></a>Новые возможности для HoloLens

Windows 10 апреля 2018 г. выпуск обновления для всех клиентов HoloLens! Это обновление содержит улучшения, добавленные с момента последнего основного выпуска программного обеспечения HoloLens в [август 2016 г.](release-notes-august-2016.md).

### <a name="for-everyone"></a>Для всех пользователей

<table>
  <tr>
    <th>Компонент</th><th>Подробности</th><th>Инструкция</th>
  </tr>
  <tr>
    <td>Авторазмещения 2D и 3D содержимого при запуске</td><td>Приложения UWP запуска или 2D 2D приложения auto местах в мире оптимального размера и расстояние при запуске вместо пользователю нужно поместить его. Если <a href="app-views.md">иммерсивные приложения</a> использует средство запуска 2D приложения вместо <a href="3d-app-launcher-design-guidance.md">запуска трехмерных приложений</a>, насыщенные приложения автоматически запускает из средства запуска приложений 2D так же как и в RS1.<br><br>Средство запуска трехмерного приложения из меню "Пуск" также автоматически местах в мире. Вместо автоматического запуска приложения, пользователи могут щелкнуть на панели запуска для запуска иммерсивные приложения. Открыт в приложении голограммы и от края трехмерного содержимого также auto местах в мире.</td><td>При открытии приложения из меню "Пуск", вам больше не нужно будет помещен в мире.<br><br>Если 2D приложение /<a href="3d-app-launcher-design-guidance.md">запуска трехмерных приложений</a> размещение не является оптимальным, их можно легко перемещать с помощью новой манипуляции гибких приложений, описанных ниже. Можно также повторно разместить содержимое запуска и трехмерных 2D приложения, о том, «Переместить это», а затем используя взглядом позволяет переместить содержимое.</td>
  </tr>
  <tr>
    <td>Манипуляции гибких приложений</td><td>Перемещать, масштабировать и поворачивать 2D и 3D-содержимого без необходимости перейти в режим «Настройка».</td><td>Чтобы переместить 2D приложения универсальной платформы Windows или средства запуска приложений 2D, просто помощи на его панели приложения и затем использовать tap + хранения + перетаскивание жест. Можно переместить трехмерного содержимого, в любом gazing в объекте и затем с помощью коснитесь + хранения + перетаскивание.<br><br>Чтобы изменить размер двухмерное содержимое, помощи в его углу. Курсор взглядом приводит к включению в курсор изменения размера, и затем коснитесь + хранения + перетащите для изменения размеров. Вы также можете двухмерное содержимое высотой или шириной, просмотрев его границ и перетащив.<br><br>Чтобы изменить размеры трехмерного содержимого, поднимите обоих рук во фрейм жестов, пальцами в позицию Готово. Вы увидите курсор превратить в состоянии с 2 мало руки. Сделать коснитесь и удерживайте жест с помощью обоих рук. Перемещение рук ближе или дальше друг от друга изменяется размер объекта. Перемещение вперед и назад относительно друг друга руки будет поворачиваться объект. Можно также изменить размер/повернуть двухмерное содержимое таким образом.</td>
  </tr>
  <tr>
    <td>2D приложения по горизонтали изменения размера с Перекомпоновка</td><td>Обеспечивают 2D приложения универсальной платформы Windows шире соотношение сторон для просмотра содержимого приложения. Например что делает приложение "Почта", чтобы показать в области предварительного просмотра.</td><td>Просто помощи на границе 2D приложению UWP см. в разделе курсор изменения размера, а затем использовать tap + хранения + перетаскивание жестов для изменения размера влево или вправо.</td>
  </tr>
  <tr>
    <td>Поддержки развернутой голосовых команд</td><td>Это можно сделать более просто с помощью голоса.</td><td>Попробуйте эти голосовые команды:<ul><li>«Перейти к Start» - откроется меню "Пуск" или завершает работу <a href="app-views.md">иммерсивные приложения</a>.</li><li>«Переместить это» - позволяет перемещать объект.</li></ul></td>
  </tr>
  <tr>
    <td>Обновленные приложения голограммы и фотографии</td><td>Обновленное приложение голограммы новый голограммы. Приложение обновленные фотографии.</td><td>Вы увидите обновленный интерфейс к приложениям голограммы и фотографии. Приложение голограммы включает несколько новых голограммы и метка maker упрощает создание текста.</td>
  </tr>
  <tr>
    <td>Улучшенная захвата смешанной реальности</td><td>Оборудование ярлык начала и окончания MRC видео.</td><td>Удерживайте увеличения громкости + стрелка вниз для 3 секунды начать запись MRC видео. И снова коснитесь или использовать жест раскрытия для завершения.</td>
  </tr>
  <tr>
    <td>Консолидированные пробелы</td><td>Упростите управление пространством для голограммы одиночными пробелами.</td><td>HoloLens автоматически находит ваше пространство и больше не требуется управлять, или выбрать пробелы. При наличии проблем с голограммы вы, можно перейти к <b>параметры > Система > голограммы > Удалить ближайших голограммы</b>. При необходимости можно также выбрать <b>удалить все голограммы</b>.</td>
  </tr>
  <tr>
    <td>Улучшенная погружения аудио</td><td>Теперь можно услышать HoloLens лучше в шумных средах и возникнуть более реалистичные средства звука из приложений, как их звук будет скрыт реальных стены, обнаруживаемые устройства.</td><td>Не нужно ничего делать слушать улучшенные пространственных звук.</td>
  </tr>
  <tr>
    <td>Проводник</td><td>Перемещение и удаление файлов из HoloLens.</td><td>Можно использовать <b>проводнике</b> приложению перемещать и удалять файлы в HoloLens.<br><br><b>Совет.</b> Если вы не видите все файлы, фильтр «Последние» может быть активен (значок часов будет выделен на левой панели). Чтобы устранить проблему, выберите <b>это устройство</b> документа значок в области слева (под значок часов), или откройте меню и выберите <b>это устройство</b>.
</td>
  </tr>
  <tr>
    <td>Поддержка MTP (протокола передачи мультимедиа)</td><td>Включает настольного компьютера для доступа к библиотекам (фотографии, видео, документы) на HoloLens для переноса данных.</td><td>Как и других мобильных устройствах, подключения к HoloLens на вашем ПК, чтобы открыть <b>проводнике</b> для доступа к библиотекам HoloLens (фотографии, видео, документы) для переноса данных.<br><br><b>Советы:</b><ul><li>Если вы не видите все файлы, убедитесь, что вход ваш HoloLens для доступа к данным.</li><li>Из <b>проводнике</b> на Компьютере, можно выбрать <b>свойства устройства</b> номер версии операционной системы Windows Holographic (версия встроенного по) и серийный номер устройства.</li></ul><b>Известные проблемы:</b> Переименование HoloLens через <b>проводнике</b> на вашем Компьютере не включен.</td>
  </tr>
  <tr>
    <td>Поддержка captive портала сети во время установки</td><td>Теперь можно настроить ваш HoloLens в сети гостевой гостиницы, центры конференции, розничными или компании, использующие captive portal.</td><td>Во время установки выберите сеть и проверьте, подключаться автоматически, при необходимости введите информацию о сети, в ответ на приглашение.</td>
  </tr>
  <tr>
    <td>Фото и видео в синхронизации с помощью приложения OneDrive</td><td>Ваши фотографии и видео с HoloLens, теперь будут синхронизироваться через приложение OneDrive из Microsoft Store, а не непосредственно через приложение "фотографии".</td><td>Чтобы настроить это, скачайте и запустите приложение OneDrive из Store. При первом запуске вам будет предложено автоматически отправляемого фотографии в OneDrive, или параметр можно найти в параметрах приложения.</td>
  </tr>
</table>

### <a name="for-developers"></a>Для разработчиков

<table>
  <tr>
    <th>Компонент</th><th>Подробности</th><th>Инструкция</th>
  </tr>
  <tr>
    <td>Усовершенствования пространственное сопоставление</td><td>Повышение качества, производительности и упрощения.</td><td>Пространственное сопоставление сетки будут отображаться очистки — меньшее число треугольников необходимых для представления уровень детализации. Вы можете заметить изменения треугольник плотность размещения в сцене.</td>
  </tr>
  <tr>
    <td>Автоматический выбор точки фокус буфер глубины</td><td>Отправка буфер глубины для Windows позволяет HoloLens выбрать точку фокуса для оптимизации стабильности голограмма, автоматически.</td><td>В Unity, перейдите в раздел <b>изменить > Параметры проекта > проигрывателя > вкладка универсальной платформы Windows > Параметры XR</b>, разверните <b>смешанной реальности SDK Windows</b> элемента и убедитесь, что <b>включить буфер глубины Совместное использование</b> проверяется. Это будет автоматически проверяться для новых проектов.<br><br>Для приложений DirectX, убедитесь, вы вызываете <a href="https://docs.microsoft.com/uwp/api/windows.graphics.holographic.holographiccamerarenderingparameters.commitdirect3d11depthbuffer">CommitDirect3D11DepthBuffer </a> метод <b>HolographicRenderingParameters</b> каждого кадра, чтобы предоставить буфер глубины для Windows.
</td>
  </tr>
  <tr>
    <td>Режимы holographic reprojection</td><td>Теперь вы можете отключить позиционные reprojection на HoloLens для повышения стабильности голограмма строго заблокирован текст содержимого, такие как видео 360 градусов.</td><td>В Unity, задайте <a href="https://docs.unity3d.com/ScriptReference/XR.WSA.HolographicSettings.ReprojectionMode.html">HolographicSettings.ReprojectionMode</a> для <a href="https://docs.unity3d.com/ScriptReference/XR.WSA.HolographicSettings.HolographicReprojectionMode.html">HolographicReprojectionMode.OrientationOnly</a> все содержимое в представлении при строго заблокирован для текста.<br><br>Для приложений DirectX, задайте <a href="https://docs.microsoft.com/uwp/api/windows.graphics.holographic.holographiccamerarenderingparameters.reprojectionmode"> HolographicCameraRenderingParameters.ReprojectionMode</a> для <a href="https://docs.microsoft.com/uwp/api/windows.graphics.holographic.holographicreprojectionmode">HolographicReprojectionMode.OrientationOnly</a> все содержимое в представлении при строго заблокирован для текста.</td>
  </tr>
  <tr>
    <td>API адаптации приложений</td><td>API-интерфейсы Windows узнать больше о где выполняется приложение, например является ли дисплей устройства прозрачного (HoloLens) или нет (иммерсивных гарнитуры) и ли двухмерном виде приложения универсальной платформы Windows, отображаются в оболочке holographic.</td><td>Unity ранее вручную представляла <a href="https://docs.unity3d.com/ScriptReference/XR.WSA.HolographicSettings.IsDisplayOpaque.html">HolographicSettings.IsDisplayOpaque</a> способом, который работал даже до этой сборки.<br><br>Для приложений DirectX, теперь вы можете просматривать существующие API-интерфейсы, такие как <a href="https://docs.microsoft.com/uwp/api/windows.graphics.holographic.holographicdisplay.isopaque">HolographicDisplay.GetDefault(). IsOpaque</a> и <a href="https://docs.microsoft.com/uwp/api/windows.applicationmodel.preview.holographic.holographicapplicationpreview.iscurrentviewpresentedonholographicdisplay">HolographicApplicationPreview.IsCurrentViewPresentedOnHolographicDisplay</a> на также HoloLens.
</td>
  </tr>
  <tr>
      <td>Режим справочные материалы</td><td>Позволяет разработчикам получать доступ к ключа датчиков HoloLens, при создании для учебных заведений и промышленных приложений для тестирования новых идей в полях компьютерного зрения и robotics, включая:<ul><li>Четыре среды отслеживания камеры</li><li>Две версии данные глубины сопоставления камеры</li><li>Две версии среды выполнения Интеграции отражательную потока</li></ul></td><td><a href="research-mode.md">Документация по режим справочные материалы</a><br><a href="https://github.com/Microsoft/HoloLensForCV">Справочные материалы режим примеров приложений</a></td>
  </tr>
</table>

### <a name="for-commercial-customers"></a>Для коммерческих клиентов

<table>
  <tr>
    <th>Компонент</th><th>Подробности</th><th>Инструкция</th>
  </tr>
  <tr>
    <td>Использование нескольких учетных записей пользователя Azure Active Directory на одном устройстве</td><td>Совместное использование HoloLens с несколькими пользователями Azure AD, каждый из которых свои собственные параметры пользователя и данные пользователя на устройстве.</td><td><a href="https://docs.microsoft.com/hololens/hololens-multiple-users">IT Pro Center: HoloLens общей папки с несколькими пользователями</a></td>
  </tr>
  <tr>
    <td>Изменять параметры сети Wi-Fi на вход</td><td>Измените Сеть Wi-Fi, прежде чем войти для включения другого пользователя выполнить вход с использованием учетной записи пользователя Azure AD свой первый раз, позволяя пользователям общий доступ к устройствам в разных расположениях и задания сайтов.</td><td>На экране входа в систему можно использовать значок сети ниже поле пароля для подключения к сети. Это полезно в том случае, если это первый раз войти в устройство.</td>
  </tr>
  <tr>
    <td>Поддержки единой регистрации</td><td>Теперь несложно, HoloLens пользователь при настройке устройства с помощью личной учетной записи Майкрософт, чтобы добавить рабочую учетную запись (Azure AD) и присоединить устройство к серверу управления мобильными Устройствами.</td><td>Просто войдите с учетной записи Azure AD и регистрации происходит автоматически.</td>
  </tr>
  <tr>
    <td>Синхронизация почты без регистрации MDM</td><td>Поддержка синхронизации почты Exchange Active Sync (EAS) без регистрации MDM.</td><td>Теперь вы можете синхронизировать сообщения электронной почты без регистрации в MDM. Можно настроить устройства с помощью учетной записи Майкрософт, загрузить и установить приложение "Почта" и добавить рабочую учетную запись электронной почты непосредственно.</td>
  </tr>
</table>

### <a name="for-it-pros"></a>ИТ-профессионалами

<table>
  <tr>
    <th>Компонент</th><th>Подробности</th><th>Инструкция</th>
  </tr>
  <tr>
    <td>Новое имя «Windows Holographic for Business» операционной системы</td><td>Очистить выпуск именования избежание путаницы на выпуск лицензию на обновление приложения, если включены функции пакет Commercial Suite на HoloLens.</td><td>Можно видеть, какую именно версию Windows Holographic на устройстве в <b>параметры > Система > о</b>. Если применить обновление выпуска, чтобы включить функции пакет Commercial Suite будет отображаться «Windows Holographic for Business». Узнайте, как <a href="https://docs.microsoft.com/hololens/hololens-upgrade-enterprise">разблокировать Windows Holographic for Business функции</a>.</td>
  </tr>
  <tr>
  <td>Конструктор конфигураций Windows (WCD)</td><td>Создавать и изменять пакеты подготовки для настройки с помощью обновленного приложения WCD HoloLens. Простой мастер HoloLens для обновления выпуска, можно настроить OOBE, регион/часовой пояс, массового токена Azure AD, сети и разработчика CSP. Расширенный редактор, отфильтровано для HoloLens поддерживаемые варианты, включая доступа и управления CSP учетной записи.</td><td><a href="https://docs.microsoft.com/hololens/hololens-provisioning">IT Pro Center: Настройка HoloLens, используя пакет подготовки</a></td>
  </tr>
  <tr>
    <td>Можно настроить программу установки (OOBE)</td><td>Скрыть калибровки, обучение жест/взглядом и экранов конфигурации Wi-Fi во время установки.</td><td><a href="https://docs.microsoft.com/hololens/hololens-provisioning#create-a-provisioning-package-for-hololens-using-the-hololens-wizard">IT Pro Center: Настройка HoloLens, используя пакет подготовки</a></td>
  </tr>
  <tr>
    <td>Массовой поддержкой токенов Azure AD</td><td>Предварительно зарегистрируйте устройство, чтобы клиент каталога Azure AD для быстрее последовательность операций настройки пользователя.</td><td><a href="https://docs.microsoft.com/hololens/hololens-provisioning">IT Pro Center: Настройка HoloLens, используя пакет подготовки</a></td>
  </tr>
  <tr>
  <td>Поставщик служб конфигурации DeveloperSetup</td><td>Разверните профиль, чтобы настроить HoloLens в режиме разработчика. Это удобно для разработки и демонстрация устройств.</td><td><a href="https://docs.microsoft.com/hololens/hololens-provisioning">IT Pro Center: Настройка HoloLens, используя пакет подготовки</a></td>
  </tr>
  <tr>
  <td>Поставщик служб конфигурации AccountManagement</td><td>Совместно использовать устройства HoloLens и удаления данных пользователя после выхода или бездействия или хранения пороговые значения для временного использования. Поддерживает учетные записи Azure AD.</td><td><a href="https://docs.microsoft.com/hololens/hololens-provisioning">IT Pro Center: Настройка HoloLens, используя пакет подготовки</a></td>
  </tr>
  <tr>
  <td>Ограниченного доступа</td><td>Назначен доступ для сотрудников первой строки или демонстрации Windows. Блокировки одним или с несколькими приложениями. Разработчику не нужно разблокировать.</td><td><a href="https://docs.microsoft.com/hololens/hololens-kiosk">IT Pro Center: Настройка HoloLens в полноэкранном режиме</a></td>
  </tr>
  <tr>
  <td>Гостевой доступ для устройств киоска</td><td>Ограниченный доступ с помощью учетной записи гостя без пароля для демонстрации Windows. Блокировки одним или с несколькими приложениями. Разработчику не нужно разблокировать.</td><td><a href="https://docs.microsoft.com/hololens/hololens-kiosk#guest">IT Pro Center: Настройка HoloLens в полноэкранном режиме</a></td>
  </tr>
  <tr>
    <td>Настройка системы диагностики (OOBE)</td><td>Получение диагностических журналов из HoloLens устранения ошибок входа в Azure AD (прежде чем центр отзывов доступна пользователю, которого входа в систему не удалось).</td><td>При сбое установки или входа в систему, выберите новую <b>собирать сведения</b> возможность получения журналов диагностики для устранения неполадок.</td>
  </tr>
  <tr>
    <td>Срок действия неопределенное пароля локальной учетной записи</td><td>Удалите перебоев в работе устройства Сброс по истечении срока действия пароля локальной учетной записи.</td><td>При подготовке локальную учетную запись, вы больше не нужно менять пароль каждые 42 дней в <b>параметры</b>, как срок действия пароля учетной записи больше не ограничен.</td>
  </tr>
  <tr>
    <td>Состояние синхронизации для управления мобильными Устройствами и сведения</td><td>Стандартных функциональных возможностей Windows для понимания MDM синхронизации состояния и сведений из в HoloLens.</td><td>Можно проверить состояние синхронизации MDM для устройств в <b>параметры > учетные записи > доступ к рабочей или учебной > Info</b>. В <b>состояния синхронизации устройств<b> разделе, можно запустить синхронизации, см. в разделе области под управлением MDM и создание и экспорт отчета об расширенную диагностику.</td>
  </tr>
</table>

## <a name="known-issues"></a>Известные проблемы

Мы сделали все возможное для доставки удобной Windows Mixed Reality, но мы по-прежнему отслеживаются некоторые известные проблемы. Если вы найдете другие, [отзыв](give-us-feedback.md).

### <a name="hololens"></a>HoloLens

#### <a name="after-update"></a>После обновления

После обновления с RS1 до RS4 на вашей HoloLens, могут возникать следующие проблемы:
* **Сброс ПИН-кодов** -3 x 3, приложения, прикрепленные к меню "Пуск" будут сброшены к значениям по умолчанию после обновления. 
* **Приложения и размещенные голограммы сброса** -приложения, помещаются в ваш мир будут удалены после обновления и нужно будет повторно разместить в своем пространстве. 
* **Центр обратной связи не может запустить немедленно** -сразу после обновления, может занять несколько минут, прежде чем можно будет запустить некоторые папки "Входящие" приложения, например центр обратной связи, хотя они обновляются. 
* **Корпоративные сертификаты Wi-Fi должны быть повторно синхронизирован** -мы изучаем проблему, требующую HoloLens должен быть подключен к другой сети в порядке для корпоративной сертификаты, чтобы быть повторно синхронизирован на устройство, прежде чем он сможет повторно подключиться к корпоративных сетях с использованием сертификатов. 
* **Не поддерживает воспроизведение видео HEVC H.265** -приложений, которые пытаются воспроизведение видео H.265 получит сообщение об ошибке. Обходным путем является [доступ к Windows Device Portal](using-the-windows-device-portal.md)выберите **приложений** на панели навигации слева и **удалить** приложение HEVC. Затем установите последнюю версию [расширение видео HEVC](https://www.microsoft.com/p/hevc-video-extensions/9nmzlz57r3t7) из Microsoft Store. Мы изучаем проблему. 

#### <a name="for-developers-updating-hololens-apps-for-devices-running-windows-10-april-2018-update"></a>Для разработчиков: обновление HoloLens приложений для устройств под управлением Windows 10 апреля 2018 г. обновление

А также отличный список [новые функции](#new-features-for-hololens), Windows 10 апреля 2018 с обновлением (RS4) для HoloLens применяет некоторые поведения кода, которые не поддерживались в предыдущих версиях:
* **Запрашивает разрешение использование важных ресурсов (камеру, микрофон т. д.)**  -RS4 на HoloLens будет обеспечивать запросов разрешений для приложений, которые вы собираетесь выполнить доступ к конфиденциальным ресурсам, таким как камера или "микрофон". Эти запросы не привел RS1 на HoloLens таким образом, если приложение принимает немедленный доступ к этим ресурсам, может произойти сбой в RS4 (даже если пользователь предоставляет разрешение на запрошенный ресурс). См. в статье в соответствующей [статье объявления возможностей приложения UWP](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations) Дополнительные сведения.
* **Вызовы к приложениям за пределами собственных** -RS4 на HoloLens будет обеспечивать правильное использование [ *Windows.System.Launcher* класс](https://docs.microsoft.com/uwp/api/Windows.System.Launcher) запустить другое приложение из собственных. Например, мы сталкивался с проблемами с приложений, вызывающих *Windows.System.Launcher.LaunchUriForResultsAsync* из потока без ASTA пользовательского интерфейса. Это удастся в RS1 на HoloLens, но RS4 требует вызова для выполнения в потоке пользовательского интерфейса.

### <a name="windows-mixed-reality-on-desktop"></a>Смешанная реальность Windows на рабочем столе

#### <a name="visual-quality"></a>Качество изображения

* Если вы заметили, что после обновления Windows 10 апреля 2018 г. что графики, чем более нечетким, прежде чем или что поле зрения ищет меньше на вашей гарнитуры, параметр автоматического производительности будет изменено для обеспечения достаточно частоты кадров на менее мощных Графическая плата (такие как Nvidia 1050). Можно вручную изменить это (на ваш выбор), перейдя по адресу **параметры > смешанной реальности > отображаемое гарнитура >. варианты возможностей > Изменение** и изменить «Автоматический» на «90» Гц. Кроме того, можно попробовать изменить **качества** (на той же странице параметров) «Высокий».

#### <a name="windows-mixed-reality-setup"></a>Программа установки Windows Mixed Reality

* При настройке Windows с помощью подключение гарнитуры, монитор ПК могут отключаться. Отключите вашей гарнитуры, чтобы включить вывод на монитор компьютера для завершения установки Windows.
* Если у вас наушники, можно пропустить Дополнительные советы при первом посещении Windows Mixed Reality home.
* Другие устройства Bluetooth могут создавать помехи с контроллерами движения. Если контроллеры движения есть проблемы подключения и связывание/отслеживания, убедитесь, что переключатель Bluetooth (если внешний ключ) подключен к опции близком и не сразу рядом с другой ключ Bluetooth. Также попробуйте выключения других периферийных устройств Bluetooth, во время сеансов Windows Mixed Reality ли он помогает.

#### <a name="games-and-apps-from-the-microsoft-store"></a>Игры и приложения из Microsoft Store

* Некоторые насыщенных графикой игры, например Forza Motorsport 7, может вызвать снижение производительности на менее эффективном ПК при воспроизведении в Windows Mixed Reality.

#### <a name="audio"></a>Звук

* Если включена на узле ПК до использования вашей гарнитуры смешанной реальности Windows Кортана, можно потерять пространственных звуковой моделирования, которые применяются к приложениям, что вы помещаете вокруг Windows Mixed Reality home. 
   * Решением проблемы является включение «Windows Sonic для наушников» на всех звуковых устройств, присоединенных к Компьютеру, даже подключение гарнитуры звуковое устройство:
      1. Щелкните левой кнопкой мыши значок динамика на панели задач рабочего стола и выберите из списка, звуковых устройств.
      2. Щелкните правой кнопкой мыши значок динамика на панели задач рабочего стола и выберите «Windows Sonic для наушников» в меню «Динамиков».
      3. Повторите эти шаги для всех устройств аудио (конечные точки).
   * Другой вариант отключение «Let Cortana реагирование на Привет, Кортана!» **параметры** > **Cortana** на рабочем столе до запуска Windows смешанной реальности.
* Когда другого мультимедийные устройства USB (например, веб-камера) использует один и тот же центр USB (внешним или внутри ПК) совместно с гарнитуры смешанной реальности Windows, в редких случаях гарнитура Джек/подключения наушников может либо вообще слышан звука или не содержат звука. Это можно исправить, ваш гарнитуры, USB-порту, который не совместно используют один и тот же центр как другое устройство или отключиться или отключить другие мультимедийные устройства USB.
* В очень редких случаях USB-концентратор узла компьютера не может предоставить достаточно возможностей, чтобы гарнитуры смешанной реальности Windows и вы можете заметить в пакетном режиме помех от наушники, подключенных к гарнитуры.

#### <a name="holograms"></a>Голограммы

* Если большое количество голограммы поместили в вашей Windows Mixed Reality home, некоторые исчезают и снова при рассмотрении возможности. Чтобы избежать этого, удалите некоторые голограммы в этой области Windows Mixed Reality home.

#### <a name="motion-controllers"></a>Контроллеры движения

* Если входные данные не направления гарнитура, контроллер движения кратко исчезнет, при, удерживаемой рядом с границ комнаты. Нажав клавишу Win + Y, чтобы убедиться, что имеется синий баннер через настольный монитор будет решить эту проблему. 
* Иногда Если щелкнуть веб-страницы в Microsoft Edge, содержимое будет масштаб вместо нажмите кнопку.

#### <a name="desktop-app-in-the-windows-mixed-reality-home"></a>Классическое приложение в Windows Mixed Reality home

* Ножницы не работает в настольном приложении.
* Классическое приложение не сохраняет параметр при повторном запуске.
* При использовании смешанной реальности портала предварительной версии на рабочем столе, при открытии классического приложения в Windows Mixed Reality home, вы можете заметить влияние бесконечный зеркальной. 
* Запуск классического приложения могут вызвать проблемы производительности на не - Ultra смешанной реальности компьютеров под управлением Windows; не рекомендуется.  
* Классическое приложение может автоматически запускать так, как невидимый окно на рабочем столе имеет фокус. 
* Настольных систем контроля учетных записей строке сделает гарнитура отображения черный, пока завершится в командной строке.

#### <a name="windows-mixed-reality-for-steamvr"></a>Windows Mixed Reality для SteamVR

* Может потребоваться запустить портал смешанной реальности после обновления для обеспечения необходимые обновления для Windows 10 апреля 2018 г. обновление завершена перед запуском SteamVR. 
* Будьте на последние версии Windows Mixed Reality для SteamVR совместимости с Windows 10 апреля 2018 г. обновление. Убедитесь, что автоматические обновления включены для смешанной реальности Windows для SteamVR, который находится в разделе «Программное обеспечение» библиотеки в поток данных.  

#### <a name="other-issues"></a>Другие проблемы

>[!IMPORTANT]
>Версию системы Windows 10 апреля 2018 г. Обновление отправлено участникам программы предварительной оценки (версия 17134.5) отсутствует часть программного обеспечения, необходимый для запуска Windows смешанной реальности. Рекомендуется избегать этой версии, при использовании смешанной реальностью Windows. 

Мы определили снижение производительности при использовании Surface Book 2 в начальном выпуске этого обновления (10.0.17134.1), который мы уже заняты решением проблемы в на исправление предстоящего обновления. Рекомендуется, чтобы ждать, пока эта проблема была исправлена до обновления вручную или Ожидание обновления развернуть обычным образом.

## <a name="provide-feedback-and-report-issues"></a>Предоставить отзыв или сообщить о проблеме

Используйте [приложение центр отзывов на ПК с Windows 10 или HoloLens](give-us-feedback.md) для предоставления отзыв или сообщить о проблеме. С помощью центра обратной связи обеспечивает все необходимые диагностические данные для упрощения наши инженеры быстро отладки и устранения проблемы.

>[!NOTE]
>Не забудьте принять приглашение, которое запрашивает, нужна ли центр отзывов на доступ к папке документы (выберите **Да** при появлении запроса).

## <a name="prior-release-notes"></a>Заметки о выпуске для предыдущих

* [Заметки о выпуске — октябрь 2017 г.](release-notes-october-2017.md)
* [Заметки о выпуске — август 2016 г.](release-notes-august-2016.md)
* [Заметки о выпуске — май 2016 г.](release-notes-may-2016.md)
* [Заметки о выпуске — март 2016 г.](release-notes-march-2016.md)

## <a name="see-also"></a>См. также
* [Поддержка иммерсивных Гарнитура (внешняя ссылка)](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/troubleshooting-windows-mixed-reality)
* [Поддержка HoloLens (внешняя ссылка)](https://support.microsoft.com/products/hololens)
* [Установка средств](install-the-tools.md)
* [Отзыв о нас](give-us-feedback.md)
