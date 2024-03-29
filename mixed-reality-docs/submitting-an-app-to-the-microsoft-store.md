---
title: Отправка приложения в Microsoft Store
description: В этой статье содержатся советы по отправке приложениях смешанной реальности для Microsoft Store, включая как упаковать и протестируйте свои приложения и советы по, которая прошла сертификацию и помочь в возможности обнаружения своего приложения в Store.
author: mattzmsft
ms.author: mazeller
ms.date: 03/21/2018
ms.topic: article
keywords: приложение, uwp, отправить, отправки, фильтры, метаданные, требования к системе, ключевые слова, wack, сертификации, пакет, appx, сбыту
ms.openlocfilehash: 4eb69fbaa22f4864305f09d5e1bf1c1860a0d31f
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59600866"
---
# <a name="submitting-an-app-to-the-microsoft-store"></a>Отправка приложения в Microsoft Store

Оба [HoloLens](hololens-hardware-details.md) и выключения питания компьютера с Windows 10 вашей [иммерсивных гарнитура](immersive-headset-hardware-details.md) запуск приложений универсальной платформы Windows. Ли при отправке приложение, которое поддерживает HoloLens или PC (или оба), будет отправлять приложение Microsoft Store через [центра партнеров](https://partner.microsoft.com/dashboard).

Если у вас нет учетной записи разработчика для центра партнеров, вы можете [Зарегистрируйтесь сегодня](https://developer.microsoft.com/store/register).

## <a name="packaging-a-mixed-reality-app"></a>Упаковка приложения смешанной реальности

### <a name="prepare-image-assets-included-in-the-appx"></a>Подготовка образа средства, включенные в AppX-файл

Существует несколько графические активы, необходимые для построения приложения в AppX-пакет для отправки Store appx, создающих инструменты. Дополнительные сведения о [плитки и значок ресурсы, касающиеся](https://msdn.microsoft.com/library/windows/apps/mt412102.aspx) на сайте MSDN.

| Необходимые средства | Рекомендуемые масштабирования | Формат изображения | Где отображается это? | 
|----------|----------|----------|------------------|
| Квадратный логотип 71 x 71 | Любой |  PNG | Н/Д | 
| Квадратная эмблема 150 x 150 | 150 x 150 (масштаб 100%) или 225 x 225 (150% масштаб) | PNG | Запустите ПИН-кодов и все приложения, (если он не указан 310 x 310), варианты поиска Store, страницы со списком Store Store Обзор, поиск Store | 
|  Широкий логотип 310 x 150 |  Любой  |  PNG  |  Н/Д | 
|  Логотип Store |  75 x 75 (150% масштаб)  |  PNG  |  Центр партнеров, приложение отчета, написать обзорную рецензию, моей библиотеки | 
|  Экран-заставка |  930 x 450 (150% масштаб)  |  PNG  |  Средство запуска 2D приложений (листа) | 

Кроме того, существуют также некоторые рекомендуемые активов, которые HoloLens можно воспользоваться преимуществами.

| Рекомендуемые ресурсы | Рекомендуемые масштабирования | Где отображается это? | 
|----------|----------|----------|
|  Квадратный логотип 310 x 310 |  310 x 310 (150% масштаб) |  Запуск ПИН-кодов и все приложения | 

### <a name="live-tile-requirements"></a>Динамическая Плитка требования

Меню "Пуск" HoloLens будет использовать с изображением, наибольшим включены квадратной плитки.

Вы можете увидеть, что некоторые приложения, опубликованные корпорацией Майкрософт имеют 3D запуска для своего приложения. Разработчики могут добавлять 3D средство запуска для своих приложений с помощью [эти инструкции](implementing-3d-app-launchers.md).

### <a name="specifying-target-and-minimum-version-of-windows"></a>Указание целевого объекта и Минимальная версия Windows

Если приложение смешанной реальности включает возможности, относящиеся к определенной версии Windows, важно указать целевой и минимальной версий платформы, которые будет поддерживать приложение универсальной Windows.

**Это особенно верно для приложений, предназначенных для [Windows Mixed Reality иммерсивную](immersive-headset-hardware-details.md), который требуется по меньшей мере Windows 10 Fall Creators Update (10.0; Сборка 16299) для правильной.**

Вам будет предложено задать целевой объект и Минимальная версия Windows, при создании нового универсального проекта Windows в Visual Studio. Можно также изменить этот параметр для существующего проекта в меню «Проект», затем «< имя вашего приложения в > свойства» в нижней части раскрывающегося меню.

![Задайте минимальное и предназначенных для версий платформы в Visual Studio 2017](images/visual-studio-min-version-500px.png)<br>
Задайте минимальное и предназначенных для версий платформы в Visual Studio

### <a name="specifying-target-device-families"></a>Указание целевых семейств устройств

Приложения Windows Mixed Reality (для обоих [HoloLens](hololens-hardware-details.md) и [иммерсивную](immersive-headset-hardware-details.md)) являются частью универсальной платформы Windows, поэтому любой пакет приложения с [предназначенных для семейства устройств](https://msdn.microsoft.com/library/windows/apps/dn986903.aspx)«Windows.Universal» — может выполняться на HoloLens или компьютеров с Windows 10 с иммерсивную. С другой стороны, если вы не укажете Семейство устройств целевой в манифесте приложения вы могут непреднамеренно открыть приложение до несоответствующих устройств Windows 10. Выполните следующие действия, чтобы указать предполагаемого семейства устройств Windows 10, а затем [еще раз убедиться, что на правильное устройство семейства выбраны при передаче пакета приложения в центре партнеров для отправки Store.](submitting-an-app-to-the-microsoft-store.md#submitting-your-mixed-reality-app-to-the-store)

Для этого поля в Visual Studio, щелкните правой кнопкой Package.appxmanifest и выберите «Просмотреть код», затем найдите поле имя TargetDeviceFamily. По умолчанию он может выглядеть следующим образом:

```
<Dependencies>
   <TargetDeviceFamily Name="Windows.Universal" MinVersion="10.0.10240.0" MaxVersionTested="10.0.10586.0" />
</Dependencies>
```

Если приложение создается для **HoloLens**, а затем убедитесь, что он устанавливается только на HoloLens, указав семейство целевого устройства «Windows.Holographic». 

```
<Dependencies>
   <TargetDeviceFamily Name="Windows.Holographic" MinVersion="10.0.10240.0" MaxVersionTested="10.0.10586.0" />
</Dependencies>
```

Если приложение создается для **Windows Mixed Reality иммерсивную**, а затем убедитесь, что он устанавливается только на компьютерах с Windows 10 с Windows 10 Fall Creators Update (требуется для смешанной реальности Windows) путем указания целевого объекта Семейство устройств «Windows.Desktop» и MinVersion для «10.0.16299.0».

```
<Dependencies>
   <TargetDeviceFamily Name="Windows.Desktop" MinVersion="10.0.16299.0" MaxVersionTested="10.0.16299.0" />
</Dependencies>
```

Наконец Если приложение должно работать на обоих **HoloLens и Windows Mixed Reality иммерсивную**, можно обеспечить приложение становится доступным только для этих семейств два устройства и одновременно гарантировать каждого предназначен для правильного Минимальная версия Windows, включив строку для каждого целевого семейства устройств с его соответствующих MinVersion.

```
<Dependencies>
   <TargetDeviceFamily Name="Windows.Desktop" MinVersion="10.0.16299.0" MaxVersionTested="10.0.16299.0" />
   <TargetDeviceFamily Name="Windows.Holographic" MinVersion="10.0.10240.0" MaxVersionTested="10.0.10586.0" />
</Dependencies>
```

Дополнительные сведения о целевой настройке семейств устройств, считывая [документация по TargetDeviceFamily UWP](https://docs.microsoft.com/uwp/schemas/appxpackage/uapmanifestschema/element-targetdevicefamily).

### <a name="associate-app-with-the-store"></a>Связать приложение с Store

В меню проекта в решении Visual Studio выберите «Store > связать приложение с Store». После этого можно протестировать сценарии покупки и уведомления в приложении. При связывании приложения с Store следующие значения загружаются в файле манифеста приложения для текущего проекта на локальном компьютере:
* Отображаемое имя пакета
* Имя пакета
* Идентификатор издателя
* Отображаемое имя издателя
* Версия

Если файл package.appxmanifest по умолчанию переопределяется путем создания пользовательского XML-файла для манифеста, нельзя связать приложение с Store. При попытке связать пользовательский файл манифеста с Store, вы увидите сообщение об ошибке.

### <a name="creating-an-upload-package"></a>Создание пакета передачи

Следуйте инструкциям в статье [универсальной Windows упаковки приложений для Windows 10](https://msdn.microsoft.com/library/hh454036.aspx#Anchor_2).

Последним шагом создания когда пакет передачи проверке пакета с помощью [комплект сертификации приложений для Windows](#windows-app-certification-kit).

Если необходимо добавить пакет специально для HoloLens в существующий продукт, который доступен на других семейств устройств Windows 10, также хотите узнать о [как номера версий могут повлиять на пакеты, которые доставляются клиентам ](https://msdn.microsoft.com/library/windows/apps/mt188602.aspx), и [распределение пакетов для разных операционных систем](https://msdn.microsoft.com/library/windows/apps/mt188601.aspx).

Общая рекомендация является наивысшим пакет номера версии, применимые к устройству будет один распространяются компанией Store.

Если пакет Windows.Universal и Windows.Holographic пакета и пакета Windows.Universal имеет более высокий номер версии, HoloLens пользователя будет загружен выше версии номеров Windows.Universal пакет вместо Windows.Holographic пакет. Существует несколько решений этой проблемы:
1. Обеспечить пакетов определенной платформы, такие как Windows.Holographic всегда имеют более высокий номер версии, чем пакеты вашей зависит от платформы, такие как зависимости Windows.Universal
2. Не упаковки приложений, как Windows.Universal при наличии определенных пакетов платформы — вместо этого пакета Windows.Universal пакета для конкретных платформ, которые нужно найти в

>[!NOTE]
> Можно объявить один пакет для применения к нескольким семействам целевого устройства

3. Создайте единый пакет Windows.Universal, который работает на всех платформах. Поддержка этой программе не слишком подробная прямо сейчас, рекомендуется использовать решения выше.

## <a name="testing-your-app"></a>Тестирование приложения

### <a name="windows-app-certification-kit"></a>Комплект сертификации приложений для Windows

При создании пакетов приложений для отправки в центр партнеров с помощью Visual Studio, мастер создания пакетов приложения предложит запускать пакеты, которые создаются в комплект сертификации приложений для Windows. Чтобы получить процесс отправки smooth к Store, лучше всего убедитесь, что [комплект сертификации приложений для Windows проверяет](https://msdn.microsoft.com/library/windows/apps/jj657973.aspx) передачи от приложения на локальном компьютере до передачи Store. Под управлением комплект сертификации приложений для Windows на удаленном HoloLens сейчас не поддерживается.

### <a name="run-on-all-targeted-device-families"></a>Запустить на всех целевых устройствах

Универсальная платформа Windows позволяет создавать одного приложения, которое выполняется во всех семейств устройств Windows 10. Тем не менее он не гарантирует, что универсальных Windows-приложений будет просто работать на всех устройствах. Прежде чем вы решили сделать приложение доступным для HoloLens или любой другой целевой семействе устройств Windows 10, важно, [тестирование приложения](testing-your-app-on-hololens.md) на каждом из этих семейств устройств, чтобы обеспечить нормальную работу.

## <a name="submitting-your-mixed-reality-app-to-the-store"></a>Отправка приложения смешанной реальности Store

При отправке приложение смешанной реальности, основанный на проекта Unity, см. в разделе это [видео](https://channel9.msdn.com/Blogs/One-Dev-Minute/How-to-publish-your-Unity-game-as-a-UWP-app) первого.

Как правило приложение, которое работает на HoloLens и/или иммерсивную Отправка Windows Mixed Reality — так же, как отправка любого приложения UWP для Microsoft Store. Когда вы закончите [приложение создано, резервируя его имя](https://docs.microsoft.com/windows/uwp/publish/create-your-app-by-reserving-a-name), необходимо следовать [контрольный список отправки UWP](https://docs.microsoft.com/windows/uwp/publish/app-submissions).

— В первую очередь, вы сможете сделать [выберите категорию и подкатегорию](https://docs.microsoft.com/windows/uwp/publish/category-and-subcategory-table) для работы в смешанной реальности. Очень важно, **выберите наиболее точную категорию для вашего приложения** , чтобы мы могли ассортимент приложения в правой категории Store и убедиться, оно отображается с помощью соответствующих поисковых запросов. **Листинг заголовок вашей виртуальной Реальности, как игра не приведет к лучшее предоставление для своего приложения,** и приложение может не отображаются в категории, которые являются дополнительные Подгонка и менее перегружены.

Тем не менее существуют четыре ключевых области в процессе отправки, где стоит производить выделение смешанной реальности конкретных:
1. В **[объявления продукта](submitting-an-app-to-the-microsoft-store.md#mixed-reality-product-declarations)** раздел [свойства](https://docs.microsoft.com/windows/uwp/publish/enter-app-properties).
2. В **[требования к системе](submitting-an-app-to-the-microsoft-store.md#mixed-reality-system-requirements)** раздел [свойства](https://docs.microsoft.com/windows/uwp/publish/enter-app-properties).
3. В **[доступность семейства устройств](submitting-an-app-to-the-microsoft-store.md#device-family-availability)** раздел [пакетов](https://docs.microsoft.com/windows/uwp/publish/upload-app-packages).
4. В некоторых из **[страницу с описанием Store](submitting-an-app-to-the-microsoft-store.md#store-listing-page)** поля.

### <a name="mixed-reality-product-declarations"></a>Объявления продукта смешанной реальности

На **[свойства](https://docs.microsoft.com/windows/uwp/publish/enter-app-properties)** странице процесса отправки приложения, вы найдете несколько параметров, связанных с смешанной реальности в **[объявления продукта](https://docs.microsoft.com/windows/uwp/publish/app-declarations)** раздел.

![Объявления продукта смешанной реальности](images/product-declarations-900px.png)<br>
Объявления продукта смешанной реальности

Во-первых необходимо определить типы устройств, для которых приложение предлагает вариант смешанной реальности. Это гарантирует, что приложение включается в смешанной реальности Windows коллекциях в Store, и отображается для пользователей, которые обращаются Store после подключения иммерсивных Гарнитура (или при просмотре Store на HoloLens).

Рядом с полем «эта возможность предназначена для смешанной реальности Windows на:»
* Проверьте **ПК** поле только в том случае, если приложение предоставляет возможности виртуальной Реальности при подключении к ПК пользователя иммерсивных гарнитуры. Этот флажок, ли приложение предназначен исключительно для запуска в иммерсивных гарнитура, или это стандартный ПК игру или приложение, которое предлагает смешанной реальности режим и/или премии содержимого при подключении гарнитуры, следует установить.
* Проверьте **HoloLens** поле только в том случае, если приложение предоставляет голографический интерфейс при его запуске в HoloLens.
* Проверьте **оба** поля, если ваше приложение предлагает смешанной реальности взаимодействия на обоих типов устройств, например [смешанной реальности Academy «Островка проекта» приложение](mixed-reality-250.md) с конференции Build 2017.

Если вы выбрали «PC» выше, необходимо задать «смешанной реальности setup» (уровень активности). Это относится только к возможности смешанной реальности, работающие на ПК, подключенный к иммерсивную, как приложения смешанной реальности на HoloLens являются world и масштабирования, и пользователь не определяет границы во время установки.
* Выберите **Seated + положение** Если приложение разработано с намерением, пользователь остается в одной позиции (примером может служить игры где будете вошла в панели авиарейса).
* Выберите **всех возможностей** разработано Если ваше приложение с намерением, пользователь проходит вокруг в пределах границ, он или она определена во время установки (примером может служить игр where шагом стороне и по признакам избавиться от атак).

### <a name="mixed-reality-system-requirements"></a>Требования к системе для смешанной реальности

На **[свойства](https://docs.microsoft.com/windows/uwp/publish/enter-app-properties)** странице процесса отправки приложения, вы найдете несколько параметров, связанных с смешанной реальности в **[требования к системе](https://docs.microsoft.com/windows/uwp/publish/enter-app-properties#system-requirements)** раздел.

![Требования к системе](images/system-reqs-800px.png)<br>
Системные требования

В этом разделе будет Определите минимальные требования к оборудованию (обязательно) и (необязательно) оборудования для вашего приложения смешанной реальности.

**Входной оборудование:**

Используйте флажки, чтобы сообщить потенциальных клиентов, если приложение поддерживает **"микрофон"** (для [голоса](voice-input.md)), **[Xbox контроллера или игровой](hardware-accessories.md#bluetooth-gamepads)**, и/или  **[контроллеров движения Windows Mixed Reality](motion-controllers.md)**. Эти сведения будут отображаться на странице сведений о приложении продукта в Store и поможет приложения включаются в коллекциях соответствующей приложения/игры (например, коллекции могут существовать для всех игр, которые поддерживают контроллеры движения).

Быть продуманным о выборе флажки «минимумом оборудования» или «рекомендуемое оборудование» для типов входных данных. 

Пример: 
* Если игры требуется движения контроллеров, но принимает голосовой ввод с помощью "микрофон", выберите «оборудованию» флажок рядом с «Windows Mixed Reality движения контроллеры», но флажок «рекомендуемое оборудование» рядом с «Микрофон». 
* Если свою игру можно воспроизвести с помощью либо контроллера/игровой или движения контроллеров Xbox, можно установить флажок «оборудованию» рядом с «контроллера Xbox или игровой» и установите флажок «рекомендуемое оборудование» рядом с «Windows Mixed Reality движения контроллеры» как контроллеры движения скорее всего будет предлагать подписки более высокого уровня, в интерфейсе из игровой.

**Насыщенные гарнитуры смешанной реальности Windows:**

Указывающее, является ли иммерсивных гарнитура необходим для использования приложения, или не является обязательным, крайне важен для уровня удовлетворенности клиентов и для образовательных учреждений.

Если ваше приложение может *только* использоваться через иммерсивных гарнитура, установите флажок «оборудованию» рядом с «Windows Mixed Reality гарнитура иммерсивных». Это будут отображаться на странице сведений о приложении продукта в Store как предупреждение над кнопкой покупки, клиенты не думаю, что они приобретения приложение, которое будет работать на своих Компьютерах, такие как традиционное классическое приложение.

Если приложение выполняется на рабочем столе, как и традиционные приложения ПК, но предлагает вариант VR при подключении иммерсивных Гарнитура (доступно ли полное содержимое приложения или только часть), установите флажок «рекомендуемое оборудование» рядом с «Windows Mixed Reality насыщенные гарнитуры.» Предупреждение не выдаст над кнопкой покупки на страницу сведений о продукте вашего приложения при подключении функций вашего приложения как традиционное классическое приложение без иммерсивных гарнитуры.

**Спецификации ПК:**

Если вы хотите приложения до любого числа пользователей иммерсивных гарнитуры смешанной реальности Windows можно, нужно будет [целевой](understanding-performance-for-mixed-reality.md) спецификации ПК для [смешанной реальности компьютеров под управлением Windows с помощью встроенной графической](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/windows-mixed-reality-minimum-pc-hardware-compatibility-guidelines).

Ли предназначено минимальные требования к ПК смешанной реальностью Windows приложения смешанной реальности, или требуется определенная конфигурация ПК (выделенный GPU из, например [ПК Windows Mixed Reality Ultra](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/windows-mixed-reality-minimum-pc-hardware-compatibility-guidelines), вы должны указать, что с помощью соответствующего Спецификации ПК в столбце «минимальное оборудование».

Если работают лучше или предлагать более высоким разрешением графика, на конкретной конфигурации компьютера или видеокарты, разработано ваше приложение смешанной реальности, следует указать соответствующие спецификациям ПК в столбце «рекомендованные оборудования».

Это применяется только, если ваше приложение смешанной реальности использует иммерсивных гарнитура, подключенное к Компьютеру. Если приложение смешанной реальности выполняется только на HoloLens, не нужно будет указать спецификации ПК, HoloLens, имеется только одна конфигурация оборудования.

### <a name="device-family-availability"></a>Доступность семейства устройств

Если вы уже [упакованные приложения правильно](https://docs.microsoft.com/windows/uwp/publish/app-package-requirements) в Visual Studio, передав ее на странице пакетов с процессом отправки приложения должен создать таблицы, определяющее какие семейства устройств, приложения будут доступны.

![Таблица доступности семейства устройств](images/device-family-table-900px.png)<br>
Таблица доступности семейства устройств

Если приложение смешанной реальности работает на иммерсивную, а затем на как минимум «Windows 10 Desktop» должен быть выбран в таблице. Если приложение смешанной реальности работает на HoloLens, а затем на как минимум «Windows 10 Holographic» должен быть выбран. Если ваше приложение работает и другие гарнитуры смешанной реальности Windows, например [смешанной реальности Academy «Островка проекта» приложение](mixed-reality-250.md), «Windows 10 Desktop» и «Windows 10 Holographic» должны быть выделены.

>[!TIP]
>Многие разработчики возникать ошибки при отправке пакета свои приложения, связанные с несоответствия между манифеста пакета и данные учетной записи приложения или издателем в центре партнеров. Часто эти ошибки можно избежать, вход в Visual Studio с той же учетной записи, связанные с учетной записью разработчика Windows (тот, который вы используете для входа в центре партнеров). Если вы используете ту же учетную запись, вы сможете связать приложение с его идентификации в Microsoft Store, прежде чем ее пакет.

![Связать приложение с Microsoft Store](images/associate-your-app-700px.png)<br>
Связать приложение с Microsoft Store в Visual Studio

### <a name="store-listing-page"></a>Страницу с описанием Store

На [листинг Store](https://docs.microsoft.com/windows/uwp/publish/create-app-store-listings) обрабатывать страницу отправки приложений, существует несколько мест, вы можете добавить полезную информацию о приложении смешанной реальности.

>[!IMPORTANT]
>Чтобы приложение правильно присвоил Store и не разрешается обнаружение клиентов Windows Mixed Reality, следует добавить **«Windows Mixed Reality»** как один из «термины для поиска» (можно найти условия поиска, разворачивая приложения «Общие поля» раздел).

![Добавление Windows Mixed Reality для поиска терминов](images/search-terms-800px.png)<br>
Добавьте «Windows Mixed Reality» для выражений поиска

## <a name="offering-a-free-trial-for-your-game-or-app"></a>Предложение бесплатной пробной версии для игры или приложения

Многие потребители будет ограничен нулевым опытом работы с виртуальной реальности перед покупкой иммерсивных гарнитуры смешанной реальности Windows. Они могут не знать, что следует ожидать от ресурсоемких игр и не может быть знакомо собственные комфорта порог в Впечатляющие возможности. Многие клиенты могут также попробовать иммерсивных гарнитуры смешанной реальности Windows на компьютерах, которые не являются эмблемой как [смешанной реальности компьютеров с ОС Windows](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/windows-mixed-reality-minimum-pc-hardware-compatibility-guidelines). Из-за эти вопросы, настоятельно рекомендуется рассмотреть предложение [бесплатной пробной версии](https://docs.microsoft.com/windows/uwp/publish/set-app-pricing-and-availability#free-trial) для платных смешанной реальности приложения или игры.

## <a name="see-also"></a>См. также
* [Смешанная реальность](mixed-reality.md)
* [Общие сведения о разработке](development-overview.md)
* [Представления приложения](app-views.md)
* [Основные сведения о производительности для смешанной реальности](understanding-performance-for-mixed-reality.md)
* [Рекомендации по производительности для Unity](performance-recommendations-for-unity.md)
* [Тестирование приложения на HoloLens](testing-your-app-on-hololens.md)
* [Windows Mixed Reality минимальное ПК совместимости рекомендаций по оборудованию](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/windows-mixed-reality-minimum-pc-hardware-compatibility-guidelines)
