---
title: Входные данные MR 210 - взглядом
description: Выполните пошаговое руководство по использованию Unity, Visual Studio и HoloLens Дополнительные сведения о концепции взглядом кодирования.
author: keveleigh
ms.author: kurtie
ms.date: 03/21/2018
ms.topic: article
keywords: holotoolkit, mixedrealitytoolkit, mixedrealitytoolkit unity, руководства, взглядом academy
ms.openlocfilehash: 076314389ec5ed70347c26d50c6a993f55da0758
ms.sourcegitcommit: aa88f6b42aa8d83e43104b78964afb506a368fb4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/02/2019
ms.locfileid: "64993547"
---
>[!NOTE]
>Учебники Academy реальности Mixed были разработаны с HoloLens (1-го поколения) и смешанной реальности Иммерсивную в виду.  Таким образом мы думаем, что это важно, чтобы эти учебники на месте для разработчиков, которые по-прежнему необходимы сведения при разработке приложений для этих устройств.  Эти руководства будут **_не_** дополняться последние наборы инструментов или взаимодействия, используемых для HoloLens 2.  Они будут сохранены, чтобы продолжить работу на поддерживаемых устройствах. Будет существовать новую серию учебников, которые будут опубликованы в будущем, демонстрируют способ разработки для HoloLens 2.  Это уведомление будет обновляться со ссылкой на эти руководства, когда они учитываются.

# <a name="mr-input-210-gaze"></a>Входные данные MR 210: Взгляд

[Помощи](gaze.md) — это первая форма входных данных, а также обсуждаются цели и осведомленности пользователя. 210 MR входных данных (также называемые обозревателе проектов) — это подробные сведения о связанных с взглядом основные понятия для смешанной реальности Windows. Мы добавим отслеживание контекста курсора и голограммы, преимуществами знает о взглядом пользователя приложения.

>[!VIDEO https://www.youtube.com/embed/yKAttGduVp0]

У нас есть понятное космонавты здесь помогут вам сведения о концепциях взглядом. В [101 основы MR](holograms-101.md), у нас было, просто за ваши взглядом простом курсоре. Сегодня переходим на шаг опережает простой курсор:

* Мы вносим курсор и наши голограммы поддержкой взглядом: как будет меняться в зависимости от где смотрит пользователь - или где пользователь является *не* поиска. Это делает их учетом контекста.
* Мы будем добавлять отзывы наших курсора и голограммы дать пользователю дополнительный контекст на то, что целевая. Эти отзывы можно Аудио- и visual.
* Мы покажем нацеливания методы, чтобы пользователи связываются с меньше целевых объектов.
* Мы покажем, как привлечь внимание пользователя к вашей голограммы с индикатором направления.
* Мы расскажут способы занять вашей голограммы с пользователем, так как она перемещается в ваш мир.

>[!IMPORTANT]
>Видео, внедренных в каждой главы ниже были записаны с использованием более старой версии Unity и смешанной реальности Toolkit. Хотя пошаговые инструкции и точной и актуальной, может появиться скрипты и визуальные элементы в соответствующих видео, становятся недействительными. Видеоролики остаются включены перемешаны и поскольку рассматриваются основные понятия по-прежнему применяются.

## <a name="device-support"></a>Поддержка устройств

<table>
<tr>
<th>Курс</th><th style="width:150px"> <a href="hololens-hardware-details.md">HoloLens</a></th><th style="width:150px"> <a href="immersive-headset-hardware-details.md">Иммерсивную</a></th>
</tr><tr>
<td>Входные данные MR 210: Взгляд</td><td style="text-align: center;"> ✔️</td><td style="text-align: center;"> ✔️</td>
</tr>
</table>

## <a name="before-you-start"></a>Прежде чем начать

### <a name="prerequisites"></a>предварительные требования

* ПК Windows 10, настроены с правильным [установлены средства](install-the-tools.md).
* Основные C# возможности программирования.
* Необходимо завершить [101 основы MR](holograms-101.md).
* Устройство HoloLens [настроенных для разработки для](using-visual-studio.md#enabling-developer-mode).

### <a name="project-files"></a>Файлы проекта

* Скачайте [файлы](https://github.com/Microsoft/HolographicAcademy/archive/Holograms-210-Gaze.zip) требуемые для проекта. Требуется компонент Unity 2017.2 или более поздней версии.
* Удаление архива файлы рабочего стола или других легко положения.

>[!NOTE]
>Если вы хотите просмотреть исходный код перед загрузкой, он имеет [на сайте GitHub](https://github.com/Microsoft/HolographicAcademy/tree/Holograms-210-Gaze).

### <a name="errata-and-notes"></a>Список ошибок и примечания

* В Visual Studio «Только мой код» должен быть отключено (флажок не установлен), в разделе Сервис -> Параметры -> "Отладка" для точки останова в коде.

## <a name="chapter-1---unity-setup"></a>Глава 1 - Установка Unity

>[!VIDEO https://www.youtube.com/embed/_Ccn6riQ6vU]

### <a name="objectives"></a>Цели

* Оптимизация Unity для разработки HoloLens.
* Импорт ресурсов и настроить сцены.
* Просмотрите космонавты HoloLens.

### <a name="instructions"></a>Инструкция

1. Запустите Unity.
2. Выберите **новый проект**.
3. Назовите проект **ModelExplorer**.
4. Введите расположение как **помощи** папку вы ранее не архивные.
5. Убедитесь, что проект присваивается **3D**.
6. Нажмите кнопку **Создание проекта**.

### <a name="unity-settings-for-hololens"></a>Параметры Unity для HoloLens

Нужно сообщить Unity известно, что следует создать приложение, мы пытаемся Экспорт [иммерсивных представление](app-views.md) вместо двухмерном виде. Для этого, добавив HoloLens в качестве устройств виртуальной реальности.

1. Перейдите к **изменить > Параметры проекта > проигрывателя**.
2. В **панели Инспектора** параметры проигрывателя, выбор **Windows Store** значок.
3. Разверните **XR параметры** группы.
4. В **визуализации** установите флажок **поддерживается виртуальной реальности** флажок, чтобы добавить новый **виртуальной реальности SDK** списка.
5. Убедитесь, что **Windows Mixed Reality** появится в списке. Если это не так, выберите **+** кнопку в нижней части списка и выберите **Windows Holographic**.

Далее нам нужно присвоить сценариев серверную часть .NET.

1. Перейдите к **изменить > Параметры проекта > проигрывателя** (по-прежнему возможно, это на предыдущем шаге).
2. В **панели Инспектора** параметры проигрывателя, выбор **Windows Store** значок.
3. В **другие параметры** конфигурации раздела, убедитесь, что **сценариев серверной части** присваивается **.NET**

Наконец мы обновим наши настройки качества достижение высокой производительности на HoloLens.

1. Перейдите к **изменить > Параметры проекта > качества**.
2. Щелкните стрелку вниз в **по умолчанию** строки под значком Windows Store.
3. Выберите **очень мало** для **Windows Store Apps**.

### <a name="import-project-assets"></a>Импорт ресурсов проекта

1. Щелкните правой кнопкой мыши **активы** папку в **проекта** панели.
2. Щелкните **Импорт пакета > пользовательского пакета**.
3. Перейдите к файлам проекта, который вы скачали и щелкните **ModelExplorer.unitypackage**.
4. Нажмите кнопку **Открыть**.
5. После загрузки пакета, щелкните **импорта** кнопки.

### <a name="setup-the-scene"></a>Программа установки сцены

1. В иерархии, удалите **Main Camera**.
2. В **HoloToolkit** откройте **ввода** папку, затем откройте **Prefabs** папки.
3. Перетаскивание **MixedRealityCameraParent** prefab из **Prefabs** папку в **иерархии**.
4. Щелкните правой кнопкой мыши **направленный свет** в иерархии и выберите **удалить**.
5. В **голограммы** папки, перетаскивать перечисленные ниже ресурсы в корне **иерархии**:
    * **AstroMan**
    * **источники света**
    * **SpaceAudioSource**
    * **SpaceBackground**
6. Запуск **режим воспроизведения** ▶ для просмотра-космонавты, годится.
7. Нажмите кнопку **режим воспроизведения** ▶ еще раз, чтобы **остановить**.
8. В **голограммы** папки, найти **Fitbox** активов и перетащите его в корневой каталог **иерархии**.
9. Выберите **Fitbox** в **иерархии** панели.
10. Перетащите **AstroMan** коллекции из **иерархии** для **голограмма коллекции** свойство Fitbox в **инспектор** панели.

### <a name="save-the-project"></a>Сохраните проект

1. Сохраните новую сцену: **Файл > Сохранить сцену как**.
2. Нажмите кнопку **новую папку** и назовите папку **сцены**.
3. Назовите файл «**ModelExplorer**"и сохраните его в **сцены** папки.

### <a name="build-the-project"></a>Построение проекта

1. В Unity, выберите **файл > Параметры сборки**.
2. Нажмите кнопку **добавьте откройте сцены** Добавление сцены.
3. Выберите **универсальной платформы Windows** в **платформы** списке и нажмите кнопку **переключить платформу**.
4. Если вы разрабатываете специально для HoloLens, задайте **целевое устройство** для **HoloLens**. В противном случае оставьте его на **любого устройства**.
5. Убедитесь, **построение** присваивается **D3D** и **SDK** имеет значение **самую новую установленную** (которое должно быть SDK 16299 или более поздней версии).
6. Щелкните **Сборка**.
7. Создание **новую папку** с именем «Приложение».
8. Одним щелчком мыши **приложения** папки.
9. Нажмите клавишу **выберите папку**.

По завершении Unity появится окно проводника.

1. Откройте **приложения** папки.
2. Откройте **решение ModelExplorer в Visual Studio**.

Если развертывание HoloLens:

1. С помощью верхней панели инструментов в Visual Studio, изменить целевой объект с отладки на **выпуска** и из ARM для **x86**.
2. Щелкните стрелку раскрывающегося списка рядом с кнопкой на локальном компьютере и выберите **удаленный компьютер**.
3. Введите **IP-адрес устройства HoloLens** и задайте режим проверки подлинности **универсальный (незашифрованный протокол)**. Нажмите кнопку **выберите**. Если вы не знаете IP-адрес устройства, найдите в **параметры > сеть и Интернет > Дополнительно**.
4. В верхней строке меню, щелкните **Отладка -> Запуск без отладки** или нажмите клавишу **Ctrl + F5**. Если это при первом развертывании к устройству, необходимо будет [свяжите его с помощью Visual Studio](using-visual-studio.md#pairing-your-device-hololens).
5. Когда приложение будет развернуто, закрыть **Fitbox** с **выберите жест**.

Если развертывание иммерсивных гарнитура:

1. С помощью верхней панели инструментов в Visual Studio, изменить целевой объект с отладки на **выпуска** и из ARM для **x64**.
2. Убедитесь, что целевой объект развертывания присваивается **локальный компьютер**.
3. В верхней строке меню, щелкните **Отладка -> Запуск без отладки** или нажмите клавишу **Ctrl + F5**.
4. Когда приложение будет развернуто, закрыть **Fitbox** , потянув триггер на контроллере движения.

## <a name="chapter-2---cursor-and-target-feedback"></a>Глава 2 - курсора и целевой объект обратной связи

>[!VIDEO https://www.youtube.com/embed/S24u0V_T7ZI]

### <a name="objectives"></a>Цели

* Курсор визуального проектирования и поведение.
* Обратная связь на основе взглядом курсора.
* Голограмма основе взглядом обратной связи.

Мы будем строить свою работу на некоторые принципы проектирования курсора, а именно:

* Курсор всегда присутствует.
* Позаботьтесь, чтобы получить слишком мал или большой курсор.
* Избегайте приложения препятствуют работе содержимого.

### <a name="instructions"></a>Инструкция

1. В **HoloToolkit\Input\Prefabs** папки, найти **InputManager** активов.
2. Перетаскивание **InputManager** на **иерархии**.
3. В **HoloToolkit\Input\Prefabs** папки, найти **курсор** активов.
4. Перетаскивание **курсор** на **иерархии**.
5. Выберите **InputManager** объекта в **иерархии**.
6. Перетащите **курсор** объекта из **иерархии** в InputManager **SimpleSinglePointerSelector** **курсор** поле в конец **инспектор**.

![Простота установки единичный выбор указателя](images/holograms210-ssps.png)

### <a name="build-and-deploy"></a>Создание и развертывание

1. Перестройте приложение из **файл > Параметры сборки**.
2. Откройте **папки приложения**.
3. Откройте **решение ModelExplorer в Visual Studio**.
4. Нажмите кнопку **Отладка -> Запуск без отладки** или нажмите клавишу **Ctrl + F5**.
5. Обратите внимание, как курсор рисуется, и ее внешний вид, если оно касается голограмма.

### <a name="instructions"></a>Инструкция

1. В **иерархии** панели, разверните узел **AstroMan**->**GEO_G**->**Back_Center** объекта.
2. Дважды щелкните **Interactible.cs** чтобы открыть его в Visual Studio.
3. Раскомментируйте в **IFocusable.OnFocusEnter()** и **IFocusable.OnFocusExit()** обратные вызовы в **Interactible.cs**. Они называются по InputManager смешанной реальности набор средств, когда фокус (или взглядом по контроллер указывает) вводит и выходит из определенных GameObject collider.

```cs
/* TODO: DEVELOPER CODING EXERCISE 2.d */

void IFocusable.OnFocusEnter()
{
    for (int i = 0; i < defaultMaterials.Length; i++)
    {
        // 2.d: Uncomment the below line to highlight the material when gaze enters.
        defaultMaterials[i].EnableKeyword("_ENVIRONMENT_COLORING");
    }
}

void IFocusable.OnFocusExit()
{
    for (int i = 0; i < defaultMaterials.Length; i++)
    {
        // 2.d: Uncomment the below line to remove highlight on material when gaze exits.
        defaultMaterials[i].DisableKeyword("_ENVIRONMENT_COLORING");
    }
}
```

>[!NOTE]
>Мы используем `EnableKeyword` и `DisableKeyword` выше. Чтобы использовать их в собственное приложение с помощью стандартных шейдера из набора средств, вам потребуется выполнить [Unity, касающиеся доступа к материалам с помощью скрипта](https://docs.unity3d.com/Manual/MaterialsAccessingViaScript.html). В этом случае мы уже включили [три варианта выделенный материал](https://github.com/Microsoft/HolographicAcademy/tree/Holograms-210-Gaze/Completed/ModelExplorer/Assets/Resources/Models/AstroMan/Materials) в папку «ресурсы» (найдите три материалы с выделением в имени).

### <a name="build-and-deploy"></a>Создание и развертывание

1. Как и раньше постройте проект и разверните HoloLens.
2. Обратите внимание, что происходит, когда взглядом предназначен для объекта и если он недопустим.

## <a name="chapter-3---targeting-techniques"></a>Глава 3 - предназначенные для методов

>[!VIDEO https://www.youtube.com/embed/TFnuLva4VJ0]

### <a name="objectives"></a>Цели

* Упростить голограммы целевой объект.
* Стабилизация естественным головной перемещений.

### <a name="instructions"></a>Инструкция

1. В **иерархии** панели, выберите **InputManager** объекта.
2. В **инспектор** панели, найти **помощи стабилизатор** скрипта. Если требуется просмотреть, щелкните его, чтобы открыть в Visual Studio.
    * Этот сценарий выполняет итерацию по выборок данных Raycast и позволяет стабилизировать взглядом пользователя для нацеливания на точность.
3. В **инспектор**, можно изменить **хранятся образцы стабильность** значение. Это значение представляет количество выборок, стабилизатор перемещается на вычисления стабилизации значения.

## <a name="chapter-4---directional-indicator"></a>Глава 4 – направленных индикаторов

>[!VIDEO https://www.youtube.com/embed/htVbJCMlj64]

### <a name="objectives"></a>Цели

* Добавление индикатора направления на курсор для поиска голограммы.

### <a name="instructions"></a>Инструкция

Мы будем использовать **DirectionIndicator.cs** файла, который:

1. Отображение индикатора направления, если пользователь не gazing в голограммы.
2. Скрыть индикатора направления, если пользователь gazing в голограммы.
3. Обновите индикатора направления, чтобы он указывал голограммы.

Начнем.

1. Щелкните **AstroMan** объекта в **иерархии** панели и **щелкните стрелку** чтобы развернуть его.
2. В **иерархии** панели, выберите **DirectionalIndicator** объекта под **AstroMan**.
3. В **инспектор** панели, щелкните **добавить компонент** кнопки.
4. В меню, введите в поле поиска **индикатором направления**. Выберите результат поиска.
5. В **иерархии** панели перетащите **курсор** объекта на **курсор** свойство в **инспектор**.
6. В **проекта** на панели **голограммы** папку путем перетаскивания **DirectionalIndicator** активов на **индикатора направления**свойство в **инспектор**.
7. Сборка и развертывание приложения.
8. Посмотрите, как объект индикатора направления помогает найти-космонавты, годится.

## <a name="chapter-5---billboarding"></a>Глава 5 - биллбординга

>[!VIDEO https://www.youtube.com/embed/qFiLr_LUACE]

### <a name="objectives"></a>Цели

* Используйте биллбординга для голограммы всегда лицевой стороной к себе.

Мы будем использовать **Billboard.cs** файла сохранить объект GameObject, ориентированного таким образом, чтобы все время лицевой пользователя.

1. В **иерархии** панели, выберите **AstroMan** объекта.
2. В **инспектор** панели, щелкните **добавить компонент** кнопки.
3. В меню, введите в поле поиска **элемент с объявлением**. Выберите результат поиска.
4. В **инспектор** задать **оси поворота** для **Y**.
5. Попробуйте! Создавайте и развертывайте приложения прямо в приложении.
6. См. в разделе, как элемент с объявлением объекта лица, которые независимо от того, как изменить точки зрения.
7. Удалите скрипт из **AstroMan** сейчас.

## <a name="chapter-6---tag-along"></a>Глава 6 - Tag-Along

>[!VIDEO https://www.youtube.com/embed/Ct8ORZAX5JU]

### <a name="objectives"></a>Цели

* Используйте Tag-Along для наших голограммы следите за нашими новостями вокруг комнате.

Как мы работаем над этой проблемы, мы будем руководствоваться следующие ограничения на проект:

* Содержимое всегда должно быть быстро немедленно.
* Содержимое не должно быть так.
* Блокировка HEAD содержимое доставляет неудобства.

Используемый здесь решение является использование подхода «tag-along».

Объект tag-along никогда полностью не оставляет представление пользователя. Можно представить вложенные tag-along как объект, ластики head пользователя. При перемещении, содержимое будет оставаться в пределах просто быстро, перемещая к краю представления, не покидая полностью. При пользователь gazes к tag-along объекта, предоставляется более полно в представление.

Мы будем использовать **SimpleTagalong.cs** файла, который:

1. Определения, является ли объект Tag-Along в пределах границ камеры.
2. В противном случае внутри усеченная разместить Tag-Along для частично в усеченная.
3. В противном случае установите Tag-Along расстоянию по умолчанию от пользователя.

Чтобы сделать это, мы сначала необходимо изменить **Interactible.cs** скрипта для вызова **TagalongAction**.

1. Изменить **Interactible.cs** , выполнив кодирования Упражнение 6.a (84 к 87 раскомментирование строки).

```cs
/* TODO: DEVELOPER CODING EXERCISE 6.a */
// 6.a: Uncomment the lines below to perform a Tagalong action.
if (interactibleAction != null)
{
    interactibleAction.PerformAction();
}
```

**InteractibleAction.cs** скрипт, сопряженные с **Interactible.cs** выполняет пользовательские действия при касании на голограммы. В этом случае мы будем использовать его специально для tag-along.

* В **сценарии** щелкните папку **TagalongAction.cs** активов, чтобы открыть в Visual Studio.
* Упражнения кодирования или изменить его на следующий:
  * В верхней части **иерархии**, в строке поиска введите **ChestButton_Center** и выберите результат.
  * В **инспектор** панели, щелкните **добавить компонент** кнопки.
  * В меню, введите в поле поиска **свои действия**. Выберите результат поиска.
  * В **голограммы** найти папку **свои** активов.
  * Выберите **ChestButton_Center** объекта в **иерархии**. Перетаскивание **свои** объекта из **проекта** на панель **инспектор** в **объекта к свои** свойство.
  * Перетащите **свои действия** объекта из **инспектор** в **Interactible действие** на **Interactible** скрипта.
* Дважды щелкните **TagalongAction** скрипт, чтобы открыть его в Visual Studio.

![Interactible настройки](images/holograms210-interactible.png)

Нам нужно добавить следующее:

* Функция PerformAction в скрипте TagalongAction (наследуется от InteractibleAction) расширяют функциональные возможности.
* Добавьте биллбординга объекту gazed при и задайте оси поворота для x и y.
* Затем добавьте простой Tag-Along объекта.

Вот наше решение из **TagalongAction.cs**:

```cs
// Copyright (c) Microsoft Corporation. All rights reserved.
// Licensed under the MIT License. See LICENSE in the project root for license information.

using HoloToolkit.Unity;
using UnityEngine;

public class TagalongAction : InteractibleAction
{
    [SerializeField]
    [Tooltip("Drag the Tagalong prefab asset you want to display.")]
    private GameObject objectToTagalong;

    private void Awake()
    {
        if (objectToTagalong != null)
        {
            objectToTagalong = Instantiate(objectToTagalong);
            objectToTagalong.SetActive(false);

            /* TODO: DEVELOPER CODING EXERCISE 6.b */

            // 6.b: AddComponent Billboard to objectToTagAlong,
            // so it's always facing the user as they move.
            Billboard billboard = objectToTagalong.AddComponent<Billboard>();

            // 6.b: AddComponent SimpleTagalong to objectToTagAlong,
            // so it's always following the user as they move.
            objectToTagalong.AddComponent<SimpleTagalong>();

            // 6.b: Set any public properties you wish to experiment with.
            billboard.PivotAxis = PivotAxis.XY; // Already the default, but provided in case you want to edit
        }
    }

    public override void PerformAction()
    {
        // Recommend having only one tagalong.
        if (objectToTagalong == null || objectToTagalong.activeSelf)
        {
            return;
        }

        objectToTagalong.SetActive(true);
    }
}
```

* Попробуйте! Сборка и развертывание приложения.
* Посмотрите, как содержимое соответствует центру точки взглядом, но не непрерывно и не блокируя его.
