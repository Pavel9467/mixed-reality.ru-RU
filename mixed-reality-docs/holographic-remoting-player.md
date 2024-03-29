---
title: Проигрыватель holographic удаленного взаимодействия
description: Holographic проигрыватель удаленного взаимодействия является сопутствующее приложение, которое подключается к ПК приложений и игр, которые поддерживают удаленное взаимодействие Holographic. Holographic удаленного взаимодействия потоковую передачу holographic из ПК вашей Microsoft HoloLens в режиме реального времени, с помощью подключения Wi-Fi.
author: JonMLyons
ms.author: jlyons
ms.date: 03/21/2018
ms.topic: article
keywords: HoloLens, удаленное взаимодействие, Holographic удаленного взаимодействия
ms.openlocfilehash: b8354295f9752e73cc9b34c1769254e49808b63f
ms.sourcegitcommit: c6b59f532a9c5818d9b25c355a174a231f5fa943
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2019
ms.locfileid: "66813719"
---
# <a name="holographic-remoting-player"></a>Проигрыватель holographic удаленного взаимодействия

Holographic проигрыватель удаленного взаимодействия является сопутствующее приложение, которое подключается к ПК приложений и игр, которые поддерживают удаленное взаимодействие Holographic. Holographic удаленного взаимодействия потоковую передачу holographic из ПК вашей Microsoft HoloLens в режиме реального времени, с помощью подключения Wi-Fi.

Holographic проигрыватель удаленного взаимодействия может использоваться только с помощью приложений, которые специально предназначены для поддержки Holographic удаленного взаимодействия.

Для HoloLens и HoloLens 2 доступна Holographic проигрыватель удаленного взаимодействия.  Приложения ПК, которые поддерживаются Holographic удаленного взаимодействия с HoloLens должны быть обновлены для поддержки Holographic Remtoing с HoloLens 2.  Обратитесь к поставщику приложения, если у вас есть вопросы о том, какие версии поддерживаются.

## <a name="connecting-to-the-holographic-remoting-player"></a>Подключение к исполнителю Holographic удаленного взаимодействия

Следуйте инструкциям вашего приложения, чтобы подключиться к Holographic проигрыватель удаленного взаимодействия. Будет необходимо ввести IP-адрес устройства HoloLens, который можно увидеть на главном экране игрока удаленного взаимодействия, следующим образом:

![Проигрыватель holographic удаленного взаимодействия](images/holographicremotingplayer.png)

Каждый раз, когда вы видите в главном окне, вы будете знать, что у вас нет подключения приложения.

Обратите внимание, что соединение удаленного взаимодействия holographic **не зашифрован**. Следует всегда использовать Holographic удаленного взаимодействия через безопасное подключение Wi-Fi, вы доверяете.

## <a name="quality-and-performance"></a>Качество и производительность

Качество и производительность работы зависит от трех факторов:
* **Голографический интерфейс, вы используете** -приложений, которые отображают содержимое с высоким разрешением или очень подробные может потребоваться быстрее ПК или быстрее беспроводного подключения.
* **Оборудование компьютера** -свой компьютер должен иметь возможность запуска и кодирования в голографический интерфейс в 60 кадров в секунду. Для видеокарты обычно рекомендуется GeForce GTX 970 или AMD Radeon R9 290 или выше. Опять же к конкретным вариантом может потребоваться более поздней версии или нижней части карточки.
* **Подключение к Wi-Fi** -вашей голографический интерфейс передаются через Wi-Fi. Используйте быстрой сети с низкой перегрузки для повышения качества. С помощью компьютера, подключенного через кабель Ethernet, вместо того чтобы Wi-Fi, может также повысить качество.

## <a name="diagnostics"></a>Диагностика

Чтобы измерить качество подключения, скажем **«включить диагностику»** while на главном экране Holographic проигрывателя удаленного взаимодействия. Когда включены диагностические сообщения, приложение будет отображать вы:
* **FPS** — среднее число отрисованные кадры проигрыватель удаленного взаимодействия получение и Подготовка к просмотру в секунду. Идеальный вариант — 60 кадров/с.
* **Задержка** -среднее количество времени, необходимое для кадра для перехода с ПК, HoloLens. Чем меньше, тем лучше. Это во многом зависит от вашей сети Wi-Fi.

В главном окне, можно сказать **«отключить диагностику»** Чтобы отключить диагностику.

## <a name="pc-system-requirements"></a>Требования к системе ПК
* Компьютер **необходимо** работать под управлением Юбилейного обновления Windows 10 или более поздней версии.
* Мы рекомендуем GeForce GTX 970 или AMD Radeon R9 290 или лучше видеокарте.
* Мы рекомендуем подключении компьютера к сети через ethernet, чтобы уменьшить количество прыжков беспроводной связи.

## <a name="see-also"></a>См. также
* [Условия лицензии на использование ПО для голографического удаленного взаимодействия](https://docs.microsoft.com/en-us/legal/mixed-reality/microsoft-holographic-remoting-software-license-terms)
* [Заявление о конфиденциальности Майкрософт](https://go.microsoft.com/fwlink/?LinkId=521839)
