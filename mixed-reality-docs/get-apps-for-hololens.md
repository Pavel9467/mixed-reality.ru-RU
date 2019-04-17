---
title: Получить приложения для HoloLens
description: Описывает установку приложений для HoloLens, как с помощью Microsoft Store и загрузки неопубликованных приложений.
author: mattzmsft
ms.author: mazeller
ms.date: 03/21/2018
ms.topic: article
keywords: Загрузка неопубликованных, нагрузки на стороне, загрузить неопубликованными, магазин, универсальной платформы Windows, приложения, установка
ms.openlocfilehash: 5042c380e3a548e5001e045676190c2349a835a0
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59597556"
---
# <a name="get-apps-for-hololens"></a>Получить приложения для HoloLens

Как устройство Windows 10 HoloLens поддерживает многих существующих приложений универсальной платформы Windows из магазина приложений, а также новые приложения, созданный специально для HoloLens. Поверх этих, вы даже можете [разрабатывать](development-overview.md) и установки приложений или их своим друзьям!

## <a name="installing-apps"></a>Установка приложений

Для установки новых приложений на вашей HoloLens тремя способами. Для установки новых приложений из Windows Store будет первым методом. Тем не менее, можно также установить приложения с помощью портала устройства или развернуть их из Visual Studio.

### <a name="from-the-microsoft-store"></a>Из Microsoft Store
1. Выполните [Блума](gestures.md#bloom) жестов, чтобы открыть [меню "Пуск"](navigating-the-windows-mixed-reality-home.md#start-menu).
2. Выберите приложение Store, а затем нажмите на размещение этой плитки в ваш мир.
3. После открытия приложения Store используйте панель поиска для поиска любой нужное приложение.
4. Выберите **получить** или **установить** на странице приложения (покупки может потребоваться).

### <a name="installing-an-application-package-with-the-device-portal"></a>Установка пакета приложения с помощью портала устройства
1. Установление подключения от [портал устройств](using-the-windows-device-portal.md) к целевому объекту HoloLens.
2. Перейдите к **приложений** страницы в области навигации слева.
3. В разделе **пакет приложения** перейдите к AppX-файл, связанный с приложением.
  >[!IMPORTANT]
  >Убедитесь в том, что ссылки на все связанные файлы зависимостей и сертификат.

4. Нажмите кнопку **Go**.

![Установка форма приложения в Windows Device Portal на Microsoft HoloLens](images/deviceportal-appmanager.jpg)<br>
С помощью Windows Device Portal для установки приложения на HoloLens

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Развертывание из Microsoft Visual Studio 2015
1. Откройте решение приложения Visual Studio (SLN-файл).
2. Откройте проект **свойства** .
3. Выберите следующую конфигурацию сборки: Master/x86/удаленный компьютер.
4. При выборе удаленного компьютера:
   * Убедитесь, что адресные точки HoloLens Wi-Fi IP-адрес.
   * Настройка проверки подлинности для универсальный (незашифрованный протокол).
5. Построение решения.
6. Нажмите кнопку **удаленный компьютер** кнопку, чтобы развернуть приложение из Компьютере разработки для вашей HoloLens. Если уже существующую сборку на HoloLens, выберите "Да", чтобы повторно установить более новую версию.<br>
  ![Удаленное развертывание машины для приложений для Microsoft HoloLens в Visual Studio](images/vs2015-remotedeployment.jpg)<br>
7. Приложение установит и автоматического запуска на вашей HoloLens.