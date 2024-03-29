---
title: Типы приложений, смешанной реальности
description: Одно из преимуществ разработки приложений для Windows Mixed Reality — это широкий спектр функций, функций, поддерживаемых платформой из полностью иммерсивным, виртуальных сред, для разделения на уровни света сведения через environmentl текущего пользователя.
author: rwinj
ms.author: willyang
ms.date: 03/21/2018
ms.topic: article
keywords: Windows Mixed Reality, разработки, шаблоны приложений
ms.openlocfilehash: 97f8039dcd9bbf8ee3d6c7be926db16b60a76b97
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59598706"
---
# <a name="types-of-mixed-reality-apps"></a>Типы приложений, смешанной реальности

Одно из преимуществ разработки приложений для Windows Mixed Reality — это широкий спектр функций от действия, которые может поддерживать платформы. Полностью иммерсивным, виртуальных сред, к светлой информации, иерархическое представление над текущей среды пользователя смешанной реальности Windows предоставляет широкий набор средств для реализации опытом. Очень важно для приложения решает, следует понять, в начале процесса разработки для где вдоль этого спектра находится взаимодействия с ними. Это решение в конечном счете повлияет на структуре разработки приложений и технологические путь для разработки приложений.

## <a name="enhanced-environment-apps-hololens-only"></a>Улучшенные среды приложений (HoloLens)

Одним из способов, смешанной реальности может дать значение пользователей является путем облегчения размещение цифровой информации или содержимое в текущей среде пользователя. Это расширенные среды приложения. Этот подход является широко применяется для приложений, где контекстные размещение цифрового содержимого в реальном мире имеет первостепенное значение и/или сохранение реальном мире среду «present» во время взаимодействия с ними является ключом. Этот подход также позволяет пользователям легко переместить из реальных задач в цифровой задачи и легко, выполнять аренды еще больше достойная предложить, смешанной реальности приложения, которые пользователь видит действительно являются частью среды.

![Улучшенные среды приложения](images/enhancedenvironmentapps-640px.jpg)<br>
*Улучшенные среды приложения*

**Примеры использования**
* Приложение «Блокнот» стиля смешанной реальности, позволяет пользователям создавать и размещать заметки вокруг своей среде
* Поместить в удобное место для просмотра телевизора приложение смешанной реальности
* Смешанной реальностью кулинарные приложение размещается над остров кухни для помощи в приготовление задачи
* Это приложение смешанной реальности, которое предоставляет пользователям чувство «рентгеновское зрение» (т. е. голограмма помещены в верхней части и имитирует объект реального мира, предоставляя пользователю см. в разделе «внутри его» голограммы)
* Заметки смешанной реальности, помещаются в фабрику, чтобы предоставить необходимые сведения работника
* Смешанная реальность wayfinding в пространстве office
* Устранение возможности смешанной реальности (т. е. возникает настольная игра стиль)
* Смешанная реальность взаимодействия приложений, такие как Скайп

## <a name="blended-environment-apps"></a>Смешанная среда приложения

Учитывая Windows Mixed Reality возможность распознавать и сопоставление среды пользователя, которая позволяет создавать слой цифровых, в котором можно полностью накладывается на пространство пользователя. Тонкий слой учитывает форму и границы среду, но приложения может потребоваться преобразование определенных элементов, лучше всего подходит для Погрузитесь в образовательную пользователя в приложении. Это называется приложение смешанной среде. В отличие от расширенной среды приложения, приложения в смешанной среде может только заниматься достаточно среду, чтобы лучше всего использовать ее состав поощряя поведение конкретного пользователя (например, поощряя перемещения или просмотра) или путем замены элементов с изменениями (кухни счетчик является практически обложка для отображения шаблона мозаики другой). Этот тип взаимодействия может даже преобразует элемент в совершенно другой объект, но по-прежнему используются Приблизительные размеры объекта в виде базового (остров кухни преобразуется в транспортной корзины в игре thriller crime).

![Смешанная среда приложения](images/blendedenvironmentapps-640px.jpg)<br>
*Смешанная среда приложения*

**Примеры использования**
* Приложение внутренней разработки смешанной реальности для рисования, стены, countertops или этажах разными цветами и шаблоны
* Приложение смешанной реальности, позволяющий автомобильной конструктору слоя новой итерации разработки для автомобиля в предстоящих обновления поверх существующей автомобиля
* Испытательной «покрытой» и заменены автономный фруктов смешанной реальности в игры для детей
* Служба поддержки «покрытой» и заменены смешанной реальности транспортная корзина в игре thriller преступления
* Зависание жизни так «покрытой» и заменены Быстрая, с помощью примерно одинаковую форму и измерения
* Приложение, которое позволяет пользователям blast отверстия стен реальный или иммерсивных world их выявить и создавать Волшебный мир

## <a name="immersive-environment-apps"></a>Среды для иммерсивных приложений

Среды для иммерсивных приложений, относятся к среде, которая полностью изменяет мир пользователя и поместить их в другое время и место. Эти среды можно вы очень реальных задач и создания мощных и thrilling взаимодействий, которые ограничены только воображением автора приложения. В отличие от приложений в смешанной среде после Windows Mixed Reality определяет пространство пользователя, приложения иммерсивной среде может полностью пропустить текущую среду пользователя и заменить его всей stock свои собственные. Эти возможности также полностью может разделить, время и место, это означает, что пользователь может подойти улиц из рим в присутствия, относительно сохраняя при этом по-прежнему в своем пространстве реального мира. Контекст среды реального мира, не могут быть важны в иммерсивной среде приложение.

![Среды для иммерсивных приложений](images/windows-mixed-reality-640px.jpg)<br>
*Среды для иммерсивных приложений*

**Примеры использования**
* Насыщенные приложения, которое позволяет пользователю Знакомство с пробелом, никак не связано с собственные (т. е. пошаговые инструкции по знаменитого стандартных по музей, популярных city)
* Насыщенные приложения, которое организует события или сценарий, связанные с пользователем (т. е. это Битва или производительности)

## <a name="see-also"></a>См. также
* [Общие сведения о разработке](development-overview.md)
* [Модель приложений](app-model.md)
* [Представления приложения](app-views.md)
