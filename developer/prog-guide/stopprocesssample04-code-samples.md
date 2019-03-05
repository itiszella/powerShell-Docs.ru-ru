---
title: Примеры кода StopProcessSample04 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc68af2b-f622-47c4-964f-b07f3d5bdf14
caps.latest.revision: 5
ms.openlocfilehash: fdb78ac93befba66041c4e45834f8a857e3670b6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862120"
---
# <a name="stopprocesssample04-code-samples"></a><span data-ttu-id="b30ef-102">Примеры кода StopProcessSample04</span><span class="sxs-lookup"><span data-stu-id="b30ef-102">StopProcessSample04 Code Samples</span></span>

<span data-ttu-id="b30ef-103">Ниже приведены примеры кода для командлета StopProc00 образца.</span><span class="sxs-lookup"><span data-stu-id="b30ef-103">Here are the code samples for the StopProc00 sample cmdlet.</span></span> <span data-ttu-id="b30ef-104">Это `Stop-Process` командлетов, которые описаны в [добавление наборов параметров для командлета](../cmdlet/adding-parameter-sets-to-a-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="b30ef-104">This is the `Stop-Process` cmdlet sample described in [Adding Parameter Sets to a Cmdlet](../cmdlet/adding-parameter-sets-to-a-cmdlet.md).</span></span> <span data-ttu-id="b30ef-105">`Stop-Process` Командлет предназначен для остановки процессов, которые можно получить с помощью командлета Get-Proc (описано в разделе [Создание свой первый командлет](../cmdlet/creating-a-cmdlet-without-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="b30ef-105">The `Stop-Process` cmdlet is designed to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](../cmdlet/creating-a-cmdlet-without-parameters.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="b30ef-106">Вы можете скачать C# (stopprocesssample04.cs) и VB.NET (stopprocesssample04.vb) для этого командлета Stop-Proc, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="b30ef-106">You can download the C# (stopprocesssample04.cs) and VB.NET (stopprocesssample04.vb) for this Stop-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="b30ef-107">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="b30ef-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="b30ef-108">Вы можете скачать C# (stopprocesssample04.cs) и VB.NET (stopprocesssample04.vb) для этого командлета Stop-Proc, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="b30ef-108">You can download the C# (stopprocesssample04.cs) and VB.NET (stopprocesssample04.vb) for this Stop-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="b30ef-109">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="b30ef-109">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="b30ef-110">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="b30ef-110">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="b30ef-111">Полный пример кода см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="b30ef-111">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="b30ef-112">Language</span><span class="sxs-lookup"><span data-stu-id="b30ef-112">Language</span></span>|<span data-ttu-id="b30ef-113">Раздел</span><span class="sxs-lookup"><span data-stu-id="b30ef-113">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="b30ef-114">C#</span><span class="sxs-lookup"><span data-stu-id="b30ef-114">C#</span></span>|[<span data-ttu-id="b30ef-115">StopProc04 (C#) пример кода</span><span class="sxs-lookup"><span data-stu-id="b30ef-115">StopProc04 (C#) Sample Code</span></span>](./stopprocesssample04-csharp-sample-code.md)|
|<span data-ttu-id="b30ef-116">VB.NET</span><span class="sxs-lookup"><span data-stu-id="b30ef-116">VB.NET</span></span>|[<span data-ttu-id="b30ef-117">StopProc04 образец кода (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="b30ef-117">StopProc04 (VB.NET) Sample Code</span></span>](./stopprocesssample04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="b30ef-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b30ef-118">See Also</span></span>

[<span data-ttu-id="b30ef-119">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b30ef-119">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="b30ef-120">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b30ef-120">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)