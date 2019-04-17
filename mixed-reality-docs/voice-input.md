---
title: Голосовой ввод
description: Голосовой ввод — это основные входные данные для HoloLens и Windows Mixed Reality иммерсивную. Голос может использоваться для команды, диктовки, Cortana и многое другое.
author: Hak0n
ms.author: hakons
ms.date: 02/24/2019
ms.topic: article
keywords: ggv голосовых, cortana, речи, входные данные
ms.openlocfilehash: 7fb5618c13ff1ed446241f744b598cfe2484ea45
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59604743"
---
# <a name="voice-input"></a>Голосовой ввод

Голос — один из ключей три вида входных на HoloLens. Он позволяет непосредственно команды голограмма без использования [жесты](gestures.md). Вы просто [помощи](gaze.md) в голограмма и говорите вашей команды. Голосовой ввод может быть естественный способ взаимодействия ваши намерения. Голосовая связь — особенно хорошо обхода сложных интерфейсов, так как она позволяет выполнять отбросьте вложенных меню с помощью одной команды.

Голосовой ввод реализована на базе [такое же ядро](https://msdn.microsoft.com/library/windows/apps/mt185615.aspx) с поддержкой речи в все другие универсальные Windows приложения.

<br>

>[!VIDEO https://www.youtube.com/embed/eHMkOpNUtR8]

## <a name="device-support"></a>Поддержка устройств

<table>
<tr>
<th>Компонент</th><th style="width:150px"> <a href="hololens-hardware-details.md">HoloLens (1-го поколения)</a></th><th style="width:150px">HoloLens 2</th><th style="width:150px"><a href="immersive-headset-hardware-details.md">Иммерсивную</a></th>
</tr><tr>
<td> Голосовой ввод</td><td style="text-align: center;"> ✔️</td><td style="text-align: center;"> ✔️</td><td style="text-align: center;"> ✔️ (с микрофона)</td>
</tr>
</table>

## <a name="the-select-command"></a>Команда «select»

Даже без специально Добавление поддержки голоса в приложение, ваши пользователи могут активировать голограммы просто произнеся «select». Это ведет себя так же, как [жест касания](gestures.md#air-tap) на HoloLens, нажатие кнопки "выбрать" [HoloLens clicker](hardware-accessories.md#hololens-clicker), или нажав триггер на [контроллера движения Windows Mixed Reality](motion-controllers.md). Будет слышать и увидеть подсказку со «выбрать» отображается в качестве подтверждения. «Select» включен с помощью алгоритма обнаружения ключевое слово пониженного энергопотребления, он всегда был доступен тебе легко сказать в любое время минимальной батареи влияние на жизнь, даже с рук с вашей стороны.

> [!NOTE]
> Дополнительные рекомендации, относящиеся к HoloLens 2 [ожидается в ближайшее время](index.md#news-and-notes).

![Например, «select» для использования голосовых команд для выбора](images/kma-voice-select-00170-800px.png)<br>
*Например, «select» для использования голосовых команд для выбора*

## <a name="hey-cortana"></a>"Привет, Кортана!"

Кроме того, можно сказать «Привет, Кортана» откроется Cortana в любое время. Вам не придется ждать ей по-прежнему предложением свой вопрос или предоставляя ей инструкцию - например, попробуйте использовать фразу «Привет, Кортана Какова погоды?» как одного предложения. Дополнительные сведения о Cortana и что можно сделать просто попросите ее! Скажем, «Привет, Кортана! что можно сказать?» и она будет извлечь список рабочее и предлагаемые команд. Если вы уже в приложении Cortana можно также щелкнуть **?** значок на боковой панели, чтобы этот же меню.

**Команды, соответствующие HoloLens**
* "Что можно говорить?"
* «Домой» или «Перейти к начала» — вместо [Блума](gestures.md#bloom) для получения [меню "Пуск"](navigating-the-windows-mixed-reality-home.md#start-menu)
* «Запустить <app>"
* «Переместить <app> здесь»
* «Снимок»
* «Начать запись»
* «Остановить запись»
* «Increase яркость»
* «Decrease яркость»
* «Увеличить громкость»
* «Увеличить громкость»
* «» Или «Выключения звука»
* «Завершение работы устройства»
* «Перезапуск устройства»
* «Перейти в спящий режим»
* «Время это?»
* «Сколько батареи у вас осталась?»
* «Вызовите <contact>"(требуется Скайп для HoloLens)

## <a name="see-it-say-it"></a>«См. в разделе, он, скажите»

HoloLens имеет модель «см. в разделе, он, скажите» для ввода голосом, где метки на кнопках сообщить пользователям, какие голосовые команды, они также могут сказать. Например при просмотре 2D приложения, пользователя можно сказать командой «Настройка», в которой они видят на панели приложения, чтобы скорректировать положение в мире приложения.

![При просмотре 2D приложения или голограмма, пользователя можно сказать командой «Настройка», в которой они видят на панели приложения, чтобы скорректировать положение в мире приложения](images/microphone-600px.png)

Когда приложения исключением из этого правила, пользователи могут легко понять что сказать для системы управления версиями. Сделать это, при gazing на кнопке, вы увидите, которой приходится сталкиваться через мгновение, если кнопка голосовым управлением и отображает команду, чтобы поговорить с «нажмите» подсказка «voice простоя».

![См. в разделе, он, скажите команды отображаются ниже кнопок](images/voice-seeitsayit-600px.png)<br>
*«Кажется, скажите» команды отображаются под кнопок*

## <a name="voice-commands-for-fast-hologram-manipulation"></a>Голосовые команды для быструю обработку голограмма

Существует также ряд голосовые команды, можно сказать, при gazing в голограмма для быстрого выполнения задач управления данными. Эти голосовые команды работают на двухмерных приложений, а также трехмерные объекты, помещенные в мире.

**Команды для работы с голограмма**
* Мне лиц
* Чем больше | Улучшения
* Меньше

## <a name="dictation"></a>Диктовка

Вместо того чтобы вводить с [воздух касания](gestures.md#air-tap), диктовки voice может оказаться более эффективным для ввода текста в приложение. Это может значительно ускорить входных данных с меньшими трудозатратами для пользователя.

![Голосовые диктовки начинается с выбора кнопки микрофона](images/micbuttonfordictation.png)<br>
*Запускает голосовой диктовки, нажав кнопку "микрофон" на клавиатуре*

Каждый раз, когда активен holographic клавиатуры, можно переключиться режим диктовки, вместо того чтобы вводить. Выберите микрофон боковой части поле ввода текста, чтобы приступить к работе.

## <a name="communication"></a>Связь

Для приложений, желающих воспользоваться преимуществами настраиваемых звукового ввода, HoloLens, предоставляемые параметры обработки, важно понимать различные [категории аудиопоток](https://msdn.microsoft.com/library/windows/desktop/hh404178(v=vs.85).aspx) может использовать приложение. Windows 10 поддерживает несколько категорий другого потока и HoloLens делает использование три из них для включения пользовательской обработки для оптимизации качество звука "микрофон", предназначенные специально для распознавания речи, связи и другие, который может использоваться для аудио внешней среды сценарии захвата (т. е. «видеокамер»).
* Категория поток AudioCategory_Communications настроенное вызов качества и речевым сопровождением сценариев и предоставляет клиенту с 16-разрядных 24 кГц mono звуковой поток голос пользователя
* Категория поток AudioCategory_Speech настраивается для распознавания речи HoloLens (Windows) и предоставляет ему поток 16-разрядных 24 кГц mono голос пользователя. В этой категории можно использовать по сторонних производителей речи, при необходимости.
* Категория поток AudioCategory_Other настроен для записи звука окружающей среды среды и предоставляет клиенту потоку стерео аудио 48 кГц 24 бита.

Все это аудио обработки используется аппаратным ускорением, это означает, что функции очистки гораздо меньше энергии, чем если же обработки было сделано на ЦП HoloLens. Избегайте запуска других входных звуковых данных, обработки ЦП системы электричества и использовать преимущества встроенных, прямой обработки звука ввода.

## <a name="troubleshooting"></a>Устранение неполадок

При возникновении любых проблемах, с помощью «select» и «Привет, Кортана», попробуйте переместить тише пробел, включение шума или голосом громче к источнику. В настоящее время все распознавания речи на HoloLens настроены и оптимизирован специально для носителями английского (США).

Для выпуска Developer Edition смешанной реальностью Windows 2017 г. логики управления аудио конечная точка будет работать (навсегда) после ведение журнала и возвращена в для настольных компьютеров после первоначального подключения HMD. До этого первого знака out/в событии после просмотра WMR OOBE пользователь будет испытывать различных проблем звук, от не содержат звука до не содержат звука, переключение в зависимости от настроек системы до подключения HMD в первый раз.

## <a name="see-also"></a>См. также
* [Голосовой ввод в DirectX](voice-input-in-directx.md)
* [Голосовой ввод в Unity](voice-input-in-unity.md)
* [Входные данные MR 212: Голоса](holograms-212.md)