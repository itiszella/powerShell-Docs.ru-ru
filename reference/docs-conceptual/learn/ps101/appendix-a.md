---
title: Приложение А. Синтаксис справки
description: В этой статье объясняется, как читать и распознавать синтаксис командлета, представленного Get-Help.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: e8e28f66c02370b098f63a0396ef8a724cf3a1bd
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "84437985"
---
# <a name="appendix-a---help-syntax"></a>Приложение А. Синтаксис справки

В следующем примере показан раздел справки **SYNTAX** командлета `Get-EventLog`.

```powershell
help Get-EventLog
```

```Output
NAME
    Get-EventLog

SYNOPSIS
    Gets the events in an event log, or a list of the event logs, on the local or remote
    computers.


SYNTAX
    Get-EventLog [-LogName] <String> [[-InstanceId] <Int64[]>] [-After <DateTime>]
    [-AsBaseObject] [-Before <DateTime>] [-ComputerName <String[]>] [-EntryType {Error |
    Information | FailureAudit | SuccessAudit | Warning}] [-Index <Int32[]>] [-Message
    <String>] [-Newest <Int32>] [-Source <String[]>] [-UserName <String[]>]
    [<CommonParameters>]

    Get-EventLog [-AsString] [-ComputerName <String[]>] [-List] [<CommonParameters>]
```

В этом примере показана только соответствующая часть справки.

Синтаксис в основном состоит из нескольких наборов открывающих и закрывающих скобок (`[]`). Они имеют два разных значения в зависимости от способа использования. Любые символы, заключенные в квадратные скобки, являются необязательными, если только это не набор пустых квадратных скобок `[]`. Пустые квадратные скобки появляются только после того, как указывается такой тип данных, как `<string[]>`. Это означает, что именно этот параметр может принимать более одного значения указанного типа данных.

Первым параметром в первом наборе параметров `Get-EventLog` является **LogName**. Параметр LogName заключен в квадратные скобки, а это значит, что он позиционный. Другими словами, указывать имя самого параметра необязательно, если оно указано в правильном положении. Данные в угловых скобках (`<>`) после имени параметра означают, что для него требуется указать отдельное **строковое** значение. Имя параметра целиком и тип данных не заключены в квадратные скобки, поэтому при использовании этого набора параметров требуется указать параметр **LogName**.

```powershell
Get-EventLog [-LogName] <String>
```

Вторым параметром является **InstanceId**. Заметьте, что и имя параметра, и тип данных полностью заключены в квадратные скобки. Это означает, что параметр **InstanceId** является необязательным. Кроме того, заметьте, что параметр **InstanceId** заключен в собственный набор квадратных скобок. Как и в случае с параметром **LogName**, это означает, что он позиционный. После типа данных указан последний набор квадратных скобок. Это означает, что он может принимать более одного значения в виде массива или списка, элементы которого разделены запятыми.

```
[[-InstanceId] <Int64[]>]
```

Второй набор параметров содержит параметр **List**. Это параметр-переключатель, потому что после имени параметра тип данных не указан. Если параметр **List** указан, появится значение **True**, если не указан, появится значение **False**.

```
[-List]
```

Сведения о синтаксисе для команды также можно получить с помощью `Get-Command` с использованием параметра **Syntax**. Это удобный ярлык, который я постоянно использую. Он позволяет мне быстро узнать, как использовать команду, не вынуждая проверять несколько страниц справочной информации. Если мне в итоге потребуются дополнительные сведения, я буду использовать фактическое содержимое справки.

```powershell
Get-Command -Name Get-EventLog -Syntax
```

```Output
Get-EventLog [-LogName] <string> [[-InstanceId] <long[]>] [-ComputerName <string[]>] [-Newest <int>]
 [-After <datetime>] [-Before <datetime>] [-UserName <string[]>] [-Index <int[]> ]
 [-EntryType <string[]>] [-Source <string[]>] [-Message <string>] [-AsBaseObject]
 [<CommonParameters>]

Get-EventLog [-ComputerName <string[]>] [-List] [-AsString] [<CommonParameters>]
```

Чем чаще вы используете справочную систему в PowerShell, тем проще становится запомнить разные нюансы. Когда вы освоите систему, использовать ее будет привычным делом.
