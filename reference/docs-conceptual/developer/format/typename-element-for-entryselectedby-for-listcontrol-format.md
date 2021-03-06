---
title: Элемент TypeName для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 5e7b73db5aa597d96141454008c5c58b1827df24
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780225"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a>Элемент TypeName для элемента EntrySelectedBy для ListControl (формат)

Указывает тип .NET, который использует эту запись представления списка. Количество типов, которое можно указать для записи списка, не ограничено.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для листентри (Format) элемент TypeName для ентриселектедби в ListControl (Format)

## <a name="syntax"></a>Синтаксис

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби для Листентри (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|Определяет типы .NET, которые используют эту запись списка или условие, которое должно существовать для использования этой записи.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .

## <a name="remarks"></a>Примечания

Каждая запись списка должна иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.

Дополнительные сведения об использовании этого элемента в представлении списка см. в разделе [представление списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В следующем примере показано, как задать набор выбора для записи в представлении списка.

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a>См. также

[Создание представления списка](./creating-a-list-view.md)

[Элемент Ентриселектедби для Листентри (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[Элемент Селектионсетнаме для Ентриселектедби для Листентри (Format)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
