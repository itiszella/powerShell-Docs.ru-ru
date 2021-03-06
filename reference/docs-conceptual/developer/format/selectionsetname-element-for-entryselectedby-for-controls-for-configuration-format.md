---
title: Элемент Селектионсетнаме для Ентриселектедби для элементов управления конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 72072d8d13e6ca22afdb9bca2e0237d29ba0594f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787569"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)

Задает набор типов .NET, использующих это определение элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент конфигурации (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления Configuration (Format) ошибка customcontrol для элемента Control в элементе Configuration (Format) Кустоментриес для ошибка customcontrol для элемента конфигурации (Format) Кустоментри для ошибка customcontrol элементов управления для элемента конфигурации (Format) ентриселектедби для кустоментри для элементов управления конфигурации (Format) селектионсетнаме для ентриселектедби для элементов управления конфигурации (Format).

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.

### <a name="attributes"></a>Атрибуты

Нет

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Примечания

Для каждого определения элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.

Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях. Дополнительные сведения об определении наборов выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).

## <a name="see-also"></a>См. также

[Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
