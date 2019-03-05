---
title: Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b7af0b2-68e6-43c3-adcc-7c58007fced8
caps.latest.revision: 13
ms.openlocfilehash: 6f7c8d9af3c1c2fbda0208148b0088161701fdbe
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861220"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="d4c49-102">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="d4c49-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="d4c49-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="d4c49-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="d4c49-104">При наличии любого из типов в этом наборе, условие выполняется.</span><span class="sxs-lookup"><span data-stu-id="d4c49-104">When any of the types in this set are present, the condition is met.</span></span>

<span data-ttu-id="d4c49-105">Элемент DefaultSettings элемент (формат) элемент EnumerableExpansions (формат) элемент EnumerableExpansions (формат) EntrySelectedBy элемента конфигурации для элемента SelectionCondition EnumerableExpansion (формат) EntrySelectedBy для Элемент SelectionSetName EnumerableExpansion (формат) для SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="d4c49-105">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d4c49-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4c49-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d4c49-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d4c49-107">Attributes and Elements</span></span>

<span data-ttu-id="d4c49-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="d4c49-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d4c49-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d4c49-109">Attributes</span></span>

<span data-ttu-id="d4c49-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="d4c49-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d4c49-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d4c49-111">Child Elements</span></span>

<span data-ttu-id="d4c49-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="d4c49-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d4c49-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d4c49-113">Parent Elements</span></span>

|<span data-ttu-id="d4c49-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="d4c49-114">Element</span></span>|<span data-ttu-id="d4c49-115">Описание</span><span class="sxs-lookup"><span data-stu-id="d4c49-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d4c49-116">Элемент SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="d4c49-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="d4c49-117">Определяет условие, которое должно существовать разверните коллекцию объектов данного определения.</span><span class="sxs-lookup"><span data-stu-id="d4c49-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d4c49-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="d4c49-118">Text Value</span></span>

<span data-ttu-id="d4c49-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="d4c49-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="d4c49-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="d4c49-120">Remarks</span></span>

<span data-ttu-id="d4c49-121">Условию выбора можно указать набора или типа .NET Framework, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="d4c49-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="d4c49-122">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="d4c49-122">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d4c49-123">Выбор наборов представляют собой общие группы объектов .NET, которые могут использоваться с любого представления, который определяет файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="d4c49-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="d4c49-124">Дополнительные сведения о создании и ссылки на наборы выделения см. в разделе [определение выбора устанавливается](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="d4c49-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4c49-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d4c49-125">See Also</span></span>

[<span data-ttu-id="d4c49-126">Определение наборов Выбор</span><span class="sxs-lookup"><span data-stu-id="d4c49-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="d4c49-127">Элемент SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="d4c49-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="d4c49-128">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4c49-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)