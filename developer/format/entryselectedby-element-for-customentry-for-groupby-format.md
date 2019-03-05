---
title: Элемент EntrySelectedBy для CustomEntry для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a317d482-73cc-4c98-a002-1357fa879cd7
caps.latest.revision: 7
ms.openlocfilehash: cf1a80e845c38d97d71f26eba63c38a550958b79
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862820"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a><span data-ttu-id="fa25c-102">Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="fa25c-102">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="fa25c-103">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="fa25c-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="fa25c-104">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="fa25c-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="fa25c-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента EntrySelectedBy GroupBy (формат) CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="fa25c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fa25c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa25c-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fa25c-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fa25c-107">Attributes and Elements</span></span>

<span data-ttu-id="fa25c-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент.</span><span class="sxs-lookup"><span data-stu-id="fa25c-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="fa25c-109">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения.</span><span class="sxs-lookup"><span data-stu-id="fa25c-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="fa25c-110">Не ограничено максимальное число дочерних элементов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="fa25c-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="fa25c-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fa25c-111">Attributes</span></span>

<span data-ttu-id="fa25c-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="fa25c-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fa25c-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fa25c-113">Child Elements</span></span>

|<span data-ttu-id="fa25c-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="fa25c-114">Element</span></span>|<span data-ttu-id="fa25c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="fa25c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fa25c-116">Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="fa25c-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="fa25c-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="fa25c-117">Optional element.</span></span><br /><br /> <span data-ttu-id="fa25c-118">Определяет условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="fa25c-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="fa25c-119">Элемент SelectionSetName для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="fa25c-119">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="fa25c-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="fa25c-120">Optional element.</span></span><br /><br /> <span data-ttu-id="fa25c-121">Задает набор типов .NET, которые используют это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fa25c-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="fa25c-122">TypeName-элемент для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="fa25c-122">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="fa25c-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="fa25c-123">Optional element.</span></span><br /><br /> <span data-ttu-id="fa25c-124">Указывает тип .NET, который использует это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fa25c-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fa25c-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fa25c-125">Parent Elements</span></span>

|<span data-ttu-id="fa25c-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="fa25c-126">Element</span></span>|<span data-ttu-id="fa25c-127">Описание</span><span class="sxs-lookup"><span data-stu-id="fa25c-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fa25c-128">Элемент CustomEntry для пользовательский элемент управления для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="fa25c-128">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="fa25c-129">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fa25c-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fa25c-130">Замечания</span><span class="sxs-lookup"><span data-stu-id="fa25c-130">Remarks</span></span>

<span data-ttu-id="fa25c-131">Выбор условия используются для определения условия, которое должен существовать для определения используемого, например если объект имеет определенное свойство или когда значения конкретного свойства или скрипта, результатом которого является `true`.</span><span class="sxs-lookup"><span data-stu-id="fa25c-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="fa25c-132">Дополнительные сведения об условиях выделения, см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="fa25c-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fa25c-133">См. также</span><span class="sxs-lookup"><span data-stu-id="fa25c-133">See Also</span></span>

[<span data-ttu-id="fa25c-134">Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="fa25c-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="fa25c-135">Элемент SelectionSetName для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="fa25c-135">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="fa25c-136">TypeName-элемент для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="fa25c-136">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="fa25c-137">Элемент CustomEntry для CustomEntries для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="fa25c-137">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="fa25c-138">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="fa25c-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)