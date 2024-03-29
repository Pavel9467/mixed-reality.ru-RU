---
title: Пространственный MR 220 - пространственных звука
description: Выполнения данного кода пошагового руководства, с помощью Unity, Visual Studio и HoloLens Дополнительные сведения о пространственных звуковой понятия.
author: keveleigh
ms.author: kurtie
ms.date: 03/21/2018
ms.topic: article
keywords: holotoolkit, mixedrealitytoolkit, mixedrealitytoolkit unity, academy, учебник, пространственных звука
ms.openlocfilehash: 50d17fe8c9a6e3f18b1309a59c9c41af982a7505
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59599016"
---
>[!NOTE]
>Учебники Academy реальности Mixed были разработаны с HoloLens (1-го поколения) и смешанной реальности Иммерсивную в виду.  Таким образом мы думаем, что это важно, чтобы эти учебники на месте для разработчиков, которые по-прежнему необходимы сведения при разработке приложений для этих устройств.  Эти руководства будут **_не_** дополняться последние наборы инструментов или взаимодействия, используемых для HoloLens 2.  Они будут сохранены, чтобы продолжить работу на поддерживаемых устройствах. Будет существовать новую серию учебников, которые будут опубликованы в будущем, демонстрируют способ разработки для HoloLens 2.  Это уведомление будет обновляться со ссылкой на эти руководства, когда они учитываются.

<br>

# <a name="mr-spatial-220-spatial-sound"></a>MR пространственных 220: Пространственное звучание

[Пространственные звук](spatial-sound.md) breathes жизнь в голограммы и обеспечивает их присутствие в наш мир. Голограммы строятся света и звука, поэтому если вы не виден вашей голограммы, пространственных звук может помочь найти их. Пространственные звук не похоже типичный звук, который бы услышать-радио, звук, который находится в трехмерном пространстве. Пространственные звуковое сопровождение внесения голограммы звука, как они навсегда, рядом с вами, или даже в голову! В этом курсе вы научитесь:

* Настройте среду разработки, чтобы использовать Microsoft пространственный звуковой сигнал.
* Используйте Пространственные звуковой сигнал для улучшения взаимодействия.
* Используете Пространственные звуковой сигнал в сочетании с пространственными сопоставление.
* Сведения о звуковой проектирования и смешение рекомендации.
* Использовать звуковой сигнал для улучшения специальные эффекты и переноса пользователя в мире смешанной реальности.

## <a name="device-support"></a>Поддержка устройств

<table>
<tr>
<th>Курс</th><th style="width:150px"> <a href="hololens-hardware-details.md">HoloLens</a></th><th style="width:150px"> <a href="immersive-headset-hardware-details.md">Иммерсивную</a></th>
</tr><tr>
<td>MR пространственных 220: Пространственное звучание</td><td style="text-align: center;"> ✔️</td><td style="text-align: center;"> ✔️</td>
</tr>
</table>

## <a name="before-you-start"></a>Прежде чем начать

### <a name="prerequisites"></a>Предварительные требования

* ПК Windows 10, настроены с правильным [установлены средства](install-the-tools.md).
* Основные C# возможности программирования.
* Необходимо завершить [101 основы MR](holograms-101.md).
* Устройство HoloLens [настроенных для разработки для](using-visual-studio.md#enabling-developer-mode).

### <a name="project-files"></a>Файлы проекта

* Скачайте [файлы](https://github.com/Microsoft/HolographicAcademy/archive/Holograms-220-SpatialSound.zip) требуемые для проекта. Требуется компонент Unity 2017.2 или более поздней версии.
  * Если вам по-прежнему требуется поддержка Unity 5.6, используйте [этого выпуска](https://github.com/Microsoft/HolographicAcademy/archive/v1.5.6-220.zip). Этот выпуск, больше не может быть актуальном состоянии.
  * Если вам по-прежнему требуется поддержка Unity 5.5, используйте [этого выпуска](https://github.com/Microsoft/HolographicAcademy/archive/v1.5.5-220.zip). Этот выпуск, больше не может быть актуальном состоянии.
  * Если вам по-прежнему требуется поддержка Unity 5.4, используйте [этого выпуска](https://github.com/Microsoft/HolographicAcademy/archive/v1.5.4-220.zip). Этот выпуск, больше не может быть актуальном состоянии.
* Удаление архива файлы рабочего стола или других легко положения.

>[!NOTE]
>Если вы хотите просмотреть исходный код перед загрузкой, он имеет [на сайте GitHub](https://github.com/Microsoft/HolographicAcademy/tree/Holograms-220-SpatialSound).

### <a name="errata-and-notes"></a>Список ошибок и примечания

* «Включить только мой код» необходимо отключить (*unchecked*) в Visual Studio в разделе Сервис -> Параметры -> Отладка для точки останова в коде.

## <a name="chapter-1---unity-setup"></a>Глава 1 - Установка Unity

### <a name="objectives"></a>Цели

* Изменение конфигурации звуковой Unity для использования Microsoft пространственный звук.
* Добавление трехмерной звук в объект в Unity.

### <a name="instructions"></a>Инструкция

* Запустите Unity.
* Выберите **откройте**.
* Перейдите к рабочего стола и найти папку вы ранее не архивные.
* Щелкните **Starting\Decibel** папку и нажмите клавишу **Выбор папки** кнопки.
* Дождитесь загрузки в Unity проекта.
* В **проекта** панели **Scenes\Decibel.unity**.
* В **иерархии** панели, разверните узел **HologramCollection** и выберите **P0LY**.
* В окне инспектора разверните **AudioSource** и обратите внимание, что не **Spatialize** "флажок".

По умолчанию подключаемый модуль spatializer Unity не загружается. Следующие действия позволит пространственный звук в проекте.

* В верхнем меню Unity, перейдите в раздел **изменить > Параметры проекта > аудио**.
* Найти **подключаемый модуль Spatializer** раскрывающийся список и выберите **MS HRTF Spatializer**.
* В **иерархии** панели, выберите **HologramCollection > P0LY**.
* В **инспектор** панели, найти **источника аудио** компонента.
* Проверьте **Spatialize** флажок.
* Перетащите **пространственных Blend** ползунок вплоть до **3D**, или введите **1** в поле ввода.

Теперь мы постройте проект в Unity и настройка решения в Visual Studio.

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
2. Откройте **решение Visual Studio децибел**.

Если развертывание HoloLens:

1. С помощью верхней панели инструментов в Visual Studio, изменить целевой объект с отладки на **выпуска** и из ARM для **x86**.
2. Щелкните стрелку раскрывающегося списка рядом с кнопкой на локальном компьютере и выберите **удаленный компьютер**.
3. Введите **IP-адрес устройства HoloLens** и задайте режим проверки подлинности **универсальный (незашифрованный протокол)**. Нажмите кнопку **выберите**. Если вы не знаете IP-адрес устройства, найдите в **параметры > сеть и Интернет > Дополнительно**.
4. В верхней строке меню, щелкните **Отладка -> Запуск без отладки** или нажмите клавишу **Ctrl + F5**. Если это при первом развертывании к устройству, необходимо будет [свяжите его с помощью Visual Studio](using-visual-studio.md#pairing-your-device---hololens-1st-gen).

Если развертывание иммерсивных гарнитура:

1. С помощью верхней панели инструментов в Visual Studio, изменить целевой объект с отладки на **выпуска** и из ARM для **x64**.
2. Убедитесь, что целевой объект развертывания присваивается **локальный компьютер**.
3. В верхней строке меню, щелкните **Отладка -> Запуск без отладки** или нажмите клавишу **Ctrl + F5**.

## <a name="chapter-2---spatial-sound-and-interaction"></a>Глава 2 - пространственных звук и взаимодействие

### <a name="objectives"></a>Цели

* Повысьте реализм голограмма, с помощью звук.
* Направьте взглядом пользователя, с помощью звук.
* Отправка отзывов жест с помощью звук.

### <a name="part-1---enhancing-realism"></a>Часть 1 - усиления реализм

#### <a name="key-concepts"></a>Основные понятия

* Spatialize голограмма звуков.
* Звуковой источников должны размещаться в соответствующем месте на голограмма.

Соответствующее расположение для звук будет зависеть голограмма. Например если она имеет человек, звуковой источник должен находиться рядом рот и не метров.

#### <a name="instructions"></a>Инструкция

Приведенные ниже инструкции будет присоединен голограмма spatialized звука.

* В **иерархии** панели, разверните узел **HologramCollection** и выберите **P0LY**.
* В **инспектор** на панели **AudioSource**, щелкните круг рядом с полем **AudioClip** и выберите **PolyHover** из всплывающего окна.
* Щелкните круг рядом с полем **вывода** и выберите **SoundEffects** из всплывающего окна.

Проект децибел использует Unity **AudioMixer** компонента для включения, настройки звука для групп звуков. Путем группирования звуки таким образом объем может регулироваться сохраняя относительный объем каждого звука.

* В **AudioSource**, разверните **3D Параметры звука**.
* Задайте **уровень Doppler** для **0**.

Установка уровня Doppler адаптации отключает в шаге шрифта, из-за перемещения (либо голограмма или пользователя). Классическим примером Doppler является быстроменяющихся автомобиля. По мере приближения прослушиватель стационарные автомобиль возрастает голос ядра. При прохождении прослушиватель с расстоянием снижает высоты тона.

### <a name="part-2---directing-the-users-gaze"></a>Часть 2. направление взглядом пользователя

#### <a name="key-concepts"></a>Основные понятия

* Использовать звуковой сигнал привлечь внимание к важным голограммы.
* Уши помогают направлять, где должен выглядеть глаза.
* Мозг имеет несколько известных ожиданиям.

Примером сохраненных ожидаемых является птиц обычно выше головах человека. Если пользователь слышит bird звука, их сделает — для поиска. Поместив «Bird» ниже пользователь может привести к их с выходом в правильном направлении звук, но не удается найти голограмма, в зависимости от исходя из предположения необходимы для поиска.

#### <a name="instructions"></a>Инструкция

Приведенные ниже инструкции включить P0LY скрыть за вас, таким образом, чтобы найти голограмма можно использовать звук.

* В **иерархии** панели, выберите **диспетчеры**.
* В **инспектор** панели, найти **обработчика ввода речи**.
* В **обработчика ввода речи**, разверните **Go скрыть**.
* Изменение **ни одна из функций** для **PolyActions.GoHide**.

![Ключевое слово: Последовательно выберите Скрыть](images/gohide.png)

### <a name="part-3---gesture-feedback"></a>Часть 3 - жест отзывов

#### <a name="key-concepts"></a>Основные понятия

* Предоставьте пользователю подтверждения положительное жестов, с помощью звука
* Не перегрузить пользователь - get слишком громкий звуки как
* Слабая звуки рабочих рекомендации - не отвлечь внимание от опыта

#### <a name="instructions"></a>Инструкция

* В **иерархии** панели, разверните узел **HologramCollection**.
* Разверните **EnergyHub** и выберите **базы**.
* В **инспектор** панели, щелкните **добавить компонент** и добавьте **обработчика жестов звук**.
* В **обработчика жестов звук**, щелкните круг рядом с полем **коллекции к работе навигации** и **клипов обновлены навигации** и выберите **RotateClick**из всплывающего окна для обоих.
* Дважды щелкните «GestureSoundHandler» загрузить в Visual Studio.

Обработчик жестов звук выполняет следующие задачи:

* Создание и настройка **AudioSource**.
* Место **AudioSource** в папке соответствующего **GameObject**.
* Воспроизводит **AudioClip** связанный с данным жестом.

#### <a name="build-and-deploy"></a>Создание и развертывание

1. В Unity, выберите **файл > Параметры сборки**.
2. Щелкните **Сборка**.
3. Одним щелчком мыши **приложения** папки.
4. Нажмите клавишу **выберите папку**.

Проверьте, что панели инструментов указано «Выпуск», «x 86"или «x64" и «Удаленное устройство». В противном случае это кодирования экземпляра Visual Studio. Может потребоваться повторно открыть решение из папки приложения.

* При появлении соответствующего запроса, перезагрузите файлы проекта.
* Как и ранее развертывание из Visual Studio.

После развертывания приложения:

* Обратите внимание, как звук изменяется при перемещении курсора P0LY.
* Скажем *«Go скрытие»* вносить P0LY переместить в расположение за вас. Найдите его с помощью звукового сигнала.
* Помощи в нижней части концентратора энергии. Коснитесь и перетащите влево или вправо для вращения голограмма и обратите внимание на то, каким образом звук щелчка подтверждает жест.

Примечание. Нет текста панель, в которой будет tag-along с вами. Оно будет содержать доступные голосовые команды, которые можно использовать на протяжении данного курса.

## <a name="chapter-3---spatial-sound-and-spatial-mapping"></a>Глава 3 - пространственное сопоставление звука и пространственных

### <a name="objectives"></a>Цели

* Подтвердите взаимодействие между голограммы и реальным миром, используя звук.
* Скрывать звук с использованием физического мира.

### <a name="part-1---physical-world-interaction"></a>Часть 1 — взаимодействие физического мира

#### <a name="key-concepts"></a>Основные понятия

* Физические объекты обычно звуковой сигнал при обнаружении рабочую область или другого объекта.
* Звук должен быть контекста, соответствующего в интерфейсе.

Например Настройка чашку таблицы следует звуковой сигнал тише чем удаление Боулдер на часть исходного состояния системы.

#### <a name="instructions"></a>Инструкция

* В **иерархии** панели, разверните узел **HologramCollection**.
* Разверните **EnergyHub**выберите **базы**.
* В **инспектор** панели, щелкните **добавить компонент** и добавьте **коснитесь на месте с звук и действие**.
* В **коснитесь, чтобы универсальный инструмент с звук и действие**:
  * Проверьте **снабдить родительского Tap**.
  * Задайте **звук размещения** для **месте**.
  * Задайте **звук Pickup** для **Pickup**.
  * Нажмите + в нижнем прямо под оба **на действие отправки** и **на действие размещения**. Перетащите из сцены в EnergyHub **None (объект)** поля.
    * В разделе **на действие отправки**, щелкните **функции нет** -> **EnergyHubBase** -> **ResetAnimation**.
    * В разделе **на действие размещения**, щелкните **функции нет** -> **EnergyHubBase** -> **OnSelect**.

![Коснитесь, чтобы универсальный инструмент с звук и действия](images/holograms220-taptoplace.png)

### <a name="part-2---sound-occlusion"></a>Часть 2 - звуковой перекрытия

#### <a name="key-concepts"></a>Основные понятия

* Звук, например, свет, может быть перекрыто.

Классический пример — concert hall. Когда прослушиватель основано за пределами компании и дверь закрыта, звуки музыкальных muffled. Также обычно наблюдается уменьшение объема. Когда дверь открыта, полный спектр звук воспроизводится фактического объема. Обычно являются более низких частот поглощает звуков с высокой частотой.

#### <a name="instructions"></a>Инструкция

* В **иерархии** панели, разверните узел **HologramCollection** и выберите **P0LY**.
* В **инспектор** панели, щелкните **добавить компонент** и добавьте **передатчика аудио**.

Класс передатчика аудио предоставляет следующие возможности:

* Восстанавливает все изменения на объем **AudioSource**.
* Выполняет **Physics.RaycastNonAlloc** от положения пользователя в направлении **GameObject** к которому **AudioEmitter** подключен.

Метод RaycastNonAlloc используется в качестве оптимизации производительности для ограничения распределения, а также количество возвращаемых результатов.

* Для каждого **IAudioInfluencer** обнаружил вызовы **ApplyEffect** метод.
* Для каждого предыдущего **IAudioInfluencer** то есть больше не обнаружены, вызов **RemoveEffect** метод.

Обратите внимание на то, что AudioEmitter обновления в масштабах человека скоростью, в отличие от каждого кадра. Это делается потому, что люди обычно не перемещать достаточно быстро для эффект, должны обновляться чаще, чем раз в квартал или половины секунды. Голограммы, teleport быстро из одного расположения в другое может нарушить работу иллюзию.

* В **иерархии** панели, разверните узел **HologramCollection**.
* Разверните **EnergyHub** и выберите **BlobOutside**.
* В **инспектор** панели, щелкните **добавить компонент** и добавьте **Occluder аудио**.
* В **Occluder аудио**, задайте **Частота сканирования** для **1500**.

Этот параметр ограничивает число частоты AudioSource до 1500 Гц и ниже.

* Задайте **тома проход** для **0.9**.

Этот параметр позволяет уменьшить объем AudioSource 90 процентов от текущего уровня.

Аудио Occluder реализует IAudioInfluencer для:

* Применить эффект проверки видимости с помощью **AudioLowPassFilter** который вкладывается в **AudioSource** управляемых купить **AudioEmitter**.
* Тома затухания применяется к AudioSource.
* Отключает эффект, задавая нейтральный частоту среза и отключение фильтра.

Используется в качестве нейтрального частота — 22 кГц (22000 Гц). Эту частоту был выбран, поскольку они находятся выше Номинальное максимальное частоту, с которой можно прослушивать по Человеческое ухо, делая не заметно влияет звука.

* В **иерархии** панели, выберите **SpatialMapping**.
* В **инспектор** панели, щелкните **добавить компонент** и добавьте **Occluder аудио**.
* В **Occluder аудио**, задайте **Частота сканирования** для **750**.

Когда несколько occluders находятся в пути между пользователем и **AudioEmitter**, наименьшее частота применяется фильтр.

* Задайте **тома проход** для **0,75**.

Когда несколько occluders находятся в пути между пользователем и **AudioEmitter**, аддитивно применяется сквозной тома.

* В **иерархии** панели, выберите **диспетчеры**.
* В **инспектор** панели, разверните узел **обработчика ввода речи**.
* В **обработчика ввода речи**, разверните **Go плата**.
* Изменение **ни одна из функций** для **PolyActions.GoCharge**.

![Ключевое слово: Go плата](images/gocharge.png)

* Разверните **здесь**.
* Изменение **ни одна из функций** для **PolyActions.ComeBack**.

![Ключевое слово: Иди сюда](images/comehere.png)

#### <a name="build-and-deploy"></a>Создание и развертывание

* Как и раньше постройте проект в Unity и развертывание в Visual Studio.

После развертывания приложения:

* Скажем *«Go плата»* иметь P0LY введите центр энергии.

Обратите внимание на изменения в звук. Это должно показаться muffled и немного тише. Если представление себя с стене или другого объекта между вами и центр энергии, можно заметить, дальнейшие muffling звука из-за их перекрытия в реальном мире.

* Скажем *«Поступать Here»* иметь P0LY оставьте концентратора энергии и располагаться перед глазами.

Обратите внимание на то, что звуковой перекрытия удаляется после P0LY выходит из центра энергии. Если вы по-прежнему перекрытия вашим отзывам, P0LY может перекрыто в реальном мире. Попробуйте переместить, чтобы убедиться, что у вас есть четкое напрямую обращаться к P0LY.

### <a name="part-3---room-models"></a>Часть 3 - систем

#### <a name="key-concepts"></a>Основные понятия

* Размер пространства предоставляет гипнотическая очередей, способствующих звуковой локализации.
* Комнаты моделей задаются для каждого-**AudioSource**.
* [MixedRealityToolkit для Unity](https://github.com/Microsoft/MixedRealityToolkit-Unity) предоставляет код для задания места модели.
* Для работы в смешанной реальности выберите модель комнаты, которая лучше всего соответствует пространства реального мира.

При создании сценария виртуальной реальности, выберите модель комнаты, которая лучше всего соответствует виртуальной среды.

## <a name="chapter-4---sound-design"></a>Глава 4 – систему

### <a name="objectives"></a>Цели

* Общие рекомендации по для эффективной звуковой схемы.
* Узнайте, смешивая методики и рекомендации.

### <a name="part-1---sound-and-experience-design"></a>Часть 1 — звук и проектирование взаимодействия

В этом разделе рассматриваются ключевые звук и рекомендации по проектированию опыт и рекомендации.

#### <a name="normalize-all-sounds"></a>Нормализовать все звуки

Это устраняет потребность в специальных вариантов кода уровней громкости в звук колокольчика, который может занять много времени и ограничивает возможность легко обновить звуковые файлы.

#### <a name="design-for-an-untethered-experience"></a>Проектирование неограниченными возможностями, которые взаимодействие

HoloLens — это полностью автономной, неограниченными возможностями, которые holographic компьютер. Пользователи могут и будут использовать своим опытом, во время перемещения. Убедитесь, что ваш аудио наборе тестов путем прохода по.

#### <a name="emit-sound-from-logical-locations-on-your-holograms"></a>Выдавать звука из логических расположения на вашей голограммы

В реальном мире dog не bark из его заключительного и голос человека он поступил не из его/ее метров. Не выдавать звуков из Непредвиденная части вашего голограммы.

Для небольших голограммы разумно звук выпуска в центре геометрии.

#### <a name="familiar-sounds-are-most-localizable"></a>Знакомые звуки доступны для наиболее локализации

Человеческий голос и музыки очень просты в локализации. Если кто-то ваше имя, вы сможете очень точно определить, какие направление документации голоса и как далеко. Короткое, незнакомой звуки довольно сложно локализировать.

#### <a name="be-cognizant-of-user-expectations"></a>Иметь представление о ожиданиям пользователей

Качества жизни играет роль в наши возможности для определения расположения звука. Это одна из причин, почему человеческий голос особенно легко локализовать. Это важно учитывать полученные ожиданий пользователей, при помещении звуков.

Например когда кто-то слышит песни bird обычно поиск, как обычно птиц над прямой видимости (находящиеся в полете или в дереве). Пользователь может включить в правильном направлении звука, но загляните в неправильный вертикальном направлении и стать путать или разочарованы, если им не удается найти голограмма нередко.

#### <a name="avoid-hidden-emitters"></a>Избежать скрытых отправители

На практике Если мы слышим звука, мы обычно позволяет определить объект, выдающей звук. Это также должен содержать значение true в своем опыте работы. Его можно, манипулируя пользователи могли слышать, знаете, из которого исходят эти звук и он не сможет отобразить объект.

Существуют некоторые исключения этой рекомендации. Например внешней звуки, такие как crickets в поле, не обязательно видимыми. Качества жизни дает нам знание источника эти звуки, без необходимости см. в разделе, его.

### <a name="part-2---sound-mixing"></a>Часть 2 - микширования

#### <a name="target-your-mix-for-70-volume-on-the-hololens"></a>Предназначенных для вашего набора для 70% томе HoloLens

Смешанной реальности возможности позволяют голограммы возникают в реальном мире. Они также должны предусматривать реальные звуки прослушивания. Целевой том 70% позволяет пользователю услышать мира их и воспроизведение звука работы.

#### <a name="hololens-at-100-volume-should-drown-out-external-sounds"></a>HoloLens 100% объема следует поток out внешних звуков

Уровень громкости 100% является наименьшей интерфейс виртуальной реальности. Визуально он переносится мир. Также должны выполняться, что необходимо воспроизвести.

#### <a name="use-the-unity-audiomixer-to-adjust-categories-of-sounds"></a>Используется для настройки категорий звуков Unity AudioMixer

При разработке на mix, часто бывает полезно для создания звукового категорий и имеют возможность увеличения или уменьшения их том как единое. Это действие сохранит масштаб каждого звука при включении быстро и легко изменения общего сочетания. Включать общие категории. звуковые эффекты, окружением, бросков голосовой и фоновую музыку.

#### <a name="mix-sounds-based-on-the-users-gaze"></a>Смешивать звуков, в зависимости от пользователя взглядом

Часто бывает полезно изменить звуковые набор взаимодействие о том, где пользователь является (или не) поиск. Часто применяются в рамках этого способа являются уменьшить уровень volume для голограммы, которые находятся вне Holographic кадра, чтобы упростить пользователям сосредоточиться на информации перед их. Другой используется для увеличения громкости звука для привлечения внимания пользователя к важное событие.

#### <a name="building-your-mix"></a>Построение состав профиля

При создании вашего набора, рекомендуется фоновое воспроизведение аудиофайлов ваш опыт и добавить слои, в зависимости от важности. Часто в результате каждого слоя, громче по сравнению с предыдущим.

Описывая состав профиля как инвертированный Воронка, с наименее важных (и обычно тихие звуки) внизу, рекомендуется для структурирования вашего mix, аналогичную следующей схеме.

![Структура звуковой mix](images/soundlevels.png)

Бросков Voice — это интересный случай. На основе на работу, вы создаете вы можете стереозвук (не локализованный) или spatialize бросков ваш голос. Два Корпорация Майкрософт опубликовала опыт проиллюстрировать отличными примерами каждого сценария.

[HoloTour](http://www.microsoft.com/store/p/holotour/9nblggh5pj87) использует стерео голос по. Когда экранного диктора описывает расположение просматривается, звук согласовано, а не различаются в зависимости от положения пользователя. Это позволяет экранного диктора для описания сцены без ведения от spatialized звуки среды.

[Фрагменты](https://www.microsoft.com/store/p/fragments/9nblggh5ggm8) использует spatialized голос по в виде детективов. Голосовые детектива используется позволяют вернуть внимание пользователя к важным говорит о том, как если бы был фактический человека в комнате. Это позволяет еще больше смысла погружения в интерфейс решения тайну.

### <a name="part-3--performance"></a>Часть 3 - производительности

#### <a name="cpu-usage"></a>Использование ЦП

При использовании пространственный звук, отправители 10-12 будет составлять примерно 12% ресурсов ЦП.

#### <a name="stream-long-audio-files"></a>Stream долго звуковые файлы

Аудиоданные могут быть большими, особенно на общих частоты выборки (кГц 44,1 и 48). Общее правило таково, что звуковые файлы, более 5 – 10 секунд должен передаваться в сократить использование памяти приложения.

В Unity можно пометить звуковой файл для потоковой передачи в параметры импорта файла.

![Параметры импорта звуковых](images/audioimportsettings.png)

## <a name="chapter-5---special-effects"></a>Глава 5 - специальные эффекты

### <a name="objectives"></a>Цели

* Добавьте «Magic Windows» глубина.
* Пользователя можно открыть в виртуальный мир.

### <a name="magic-windows"></a>Magic Windows

#### <a name="key-concepts"></a>Основные понятия

* Создание представлений в скрытый мир, — визуально привлекательные.
* Улучшить реализм, добавив звуковые эффекты, когда голограмма или пользователь приближается к скрытым всему миру.

#### <a name="instructions"></a>Инструкция

* В **иерархии** панели, разверните узел **HologramCollection** и выберите **Underworld**.
* Разверните **Underworld** и выберите **VoiceSource**.
* В **инспектор** панели, щелкните **добавить компонент** и добавьте **эффект голос пользователя**.

**AudioSource** добавляется компонент **VoiceSource**.

* В **AudioSource**, задайте **вывода** для **UserVoice (Mixer)**.
* Проверьте **Spatialize** флажок.
* Перетащите **пространственных Blend** ползунок вплоть до **3D**, или введите **1** в поле ввода.
* Разверните **3D Параметры звука**.
* Задайте **уровень Doppler** для **0**.
* В **эффект голос пользователя**, задайте **родительский объект** для **Underworld** из сцены.
* Задайте **максимальное расстояние** для **1**.

Установка **максимальное расстояние** сообщает **эффект голос пользователя** как близко пользователь должен быть к родительскому объекту до включения эффекта.

* В **эффект голос пользователя**, разверните **параметры горячее**.
* Задайте **глубина** для **0,1**.
* Задайте **коснитесь один том**, **коснитесь 2 тома** и **коснитесь 3 тома** для **0,8**.
* Задайте **исходный Громкость** для **0,5**.

Предыдущие параметры настройки параметров Unity **AudioChorusFilter** используется для добавления пути расширения возможностей голосовой связи.

* В **эффект голос пользователя**, разверните **Echo параметры**.
* Задайте **задержка** для **300**
* Задайте **Decay соотношение** для **0,2**.
* Задайте **исходный Громкость** для **0**.

Предыдущие параметры настройки параметров Unity **AudioEchoFilter** использован голос пользователя для обратной передачи.

Скрипт эффект голос пользователя отвечает за:

* Измерение расстояния между пользователем и **GameObject** к которому присоединена скрипт.
* Определить, имеются ли пользователь **GameObject**.

Пользователь должен с выходом GameObject, независимо от расстояния для эффекта, который требуется включить.

* Применение и настройка **AudioChorusFilter** и **AudioEchoFilter** для **AudioSource**.
* Отключение эффекта, отключив фильтры.

Эффект голос пользователя использует компонент селектор Stream Mic из [MixedRealityToolkit для Unity](https://github.com/Microsoft/MixedRealityToolkit-Unity), чтобы выбрать поток высокое качество голосовой и направить ее в аудио система Unity.

* В **иерархии** панели, выберите **диспетчеры**.
* В **инспектор** панели, разверните узел **обработчика ввода речи**.
* В **обработчика ввода речи**, разверните **Показать Underworld**.
* Изменение **ни одна из функций** для **UnderworldBase.OnEnable**.

![Ключевое слово: Показать Underworld](images/showunderworld.png)

* Разверните **скрыть Underworld**.
* Изменение **ни одна из функций** для **UnderworldBase.OnDisable**.

![Ключевое слово: Скрыть Underworld](images/hideunderworld.png)

#### <a name="build-and-deploy"></a>Создание и развертывание

* Как и раньше постройте проект в Unity и развертывание в Visual Studio.

После развертывания приложения:

* Лиц поверхности (по часам, floor, таблицы) и say *«Показать Underworld»*.

Underworld будет отображаться, и все другие голограммы будут скрыты. Если вы не видите underworld, убедитесь, что, с которыми сталкиваются поверхность реального мира.

* Подход в пределах 1 метра от underworld голограмма и начать разговор.

Теперь есть звуковые эффекты применены к свой голос!

* Откажутся от underworld и обратите внимание на то, как больше не применяется эффект.
* Скажем *«Скрыть Underworld»* скрыть underworld.

Underworld будут скрыты и ранее скрытые голограммы появится на экране.

## <a name="the-end"></a>Конец

Поздравляем! Вы завершили **пространственных 220 MR: Пространственные звук**.

Ожидать передачи всему миру и Оживите своим опытом со звуком!
