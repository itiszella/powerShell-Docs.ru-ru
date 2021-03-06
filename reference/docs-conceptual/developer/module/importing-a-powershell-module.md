---
title: Импорт модуля PowerShell | Документация Майкрософт
ms.date: 02/03/2020
ms.openlocfilehash: 8cd1938d0a7b49b4a594753d8ce5ebe60625025d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784883"
---
# <a name="importing-a-powershell-module"></a>Импорт модуля PowerShell

После установки модуля в системе может потребоваться импортировать модуль. Импорт — это процесс, который загружает модуль в активную память, чтобы пользователь мог получить доступ к этому модулю в сеансе PowerShell. В PowerShell 2,0 можно импортировать недавно установленный модуль PowerShell с помощью вызова командлета [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) . В PowerShell 3,0 PowerShell может неявно импортировать модуль, когда пользователь вызывает одну из функций или командлетов в модуле. Обратите внимание, что в обеих версиях предполагается, что модуль устанавливается в расположение, где PowerShell может его найти. Дополнительные сведения см. [в разделе Установка модуля PowerShell](./installing-a-powershell-module.md).
Манифест модуля можно использовать для ограничения экспортируемых частей модуля, и можно использовать параметры `Import-Module` вызова, чтобы ограничить импортируемые части.

## <a name="importing-a-snap-in-powershell-10"></a>Импорт оснастки (PowerShell 1,0)

Модули не существовали в PowerShell 1,0. вместо этого необходимо было зарегистрировать и использовать оснастки. Однако мы не рекомендуем использовать эту технологию на этом этапе, так как модули обычно проще устанавливать и импортировать. Дополнительные сведения см. в разделе [Создание оснастки Windows PowerShell](../cmdlet/how-to-create-a-windows-powershell-snap-in.md).

## <a name="importing-a-module-with-import-module-powershell-20"></a>Импорт модуля с помощью Import-Module (PowerShell 2,0)

Для импорта модулей в PowerShell 2,0 используется командлет [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) с соответствующим именем. При запуске этого командлета Windows PowerShell ищет указанный модуль в каталогах, указанных в `PSModulePath` переменной. При обнаружении указанного каталога Windows PowerShell ищет файлы в следующем порядке: файлы манифеста модуля (. PSD1), файлы модулей скриптов (. PSM1), двоичные файлы модулей (. dll). Дополнительные сведения о добавлении каталогов в поиск см. в разделе [изменение пути установки PSModulePath](./modifying-the-psmodulepath-installation-path.md).
В следующем примере кода показано, как импортировать модуль:

```powershell
Import-Module myModule
```

Если предположить, что она была размещена в `PSModulePath` , PowerShell загрузит myModule в активную память. Если она не была расположена по `PSModulePath` пути, можно по-прежнему указать PowerShell, где его найти:

```powershell
Import-Module -Name C:\myRandomDirectory\myModule -Verbose
```

Можно также использовать параметр, `-Verbose` чтобы определить, что экспортируется из модуля и что импортируется в активную память. Экспорт и импорт ограничивают содержимое, доступное пользователю. разница заключается в том, кто управляет видимостью. По сути, экспорты управляются кодом внутри модуля. В отличие от этого, управление импортом осуществляется с помощью `Import-Module` вызова. Дополнительные сведения см. в разделе **запрещение импортируемых элементов**ниже.

## <a name="implicitly-importing-a-module-powershell-30"></a>Неявный импорт модуля (PowerShell 3,0)

Начиная с Windows PowerShell 3.0, модули импортируются автоматически, когда любой командлет или любая функция из модуля используются в команде. Эта функция работает для любого модуля в каталоге, который входит в значение переменной среды **PSModulePath** . Если вы не сохраните модуль по действительному пути, вы по-прежнему можете загрузить их с помощью явного параметра [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) , описанного выше.

Следующие действия активируют автоматический импорт модуля, также известный как "Автоматическая загрузка модуля".

- Использование командлета в команде. Например, при вводе `Get-ExecutionPolicy` импортируется модуль Microsoft. PowerShell. Security, содержащий `Get-ExecutionPolicy` командлет.

- Использование командлета [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) для получения команды. Например, при вводе `Get-Command Get-JobTrigger` импортируется модуль **PSScheduledJob** , содержащий `Get-JobTrigger` командлет. `Get-Command`Команда, содержащая подстановочные знаки, считается обнаружением и не инициирует импорт модуля.

- Использование командлета [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) для получения справки по командлету. Например, при вводе `Get-Help Get-WinEvent` импортируется модуль Microsoft. PowerShell. Diagnostics, содержащий `Get-WinEvent` командлет.

Для поддержки автоматического импорта модулей `Get-Command` командлет получает все командлеты и функции во всех установленных модулях, даже если модуль не импортируется в сеанс. Дополнительные сведения см. в разделе справки по командлету [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) .

## <a name="the-importing-process"></a>Процесс импорта

При импорте модуля для модуля создается новое состояние сеанса, а в памяти создается объект [System. Management. Automation. PSModuleInfo](/dotnet/api/System.Management.Automation.PSModuleInfo) . Состояние сеанса создается для каждого импортируемого модуля (включая корневой модуль и все вложенные модули). Элементы, экспортированные из корневого модуля, включая все элементы, экспортированные в корневой модуль любыми вложенными модулями, затем импортируются в состояние сеанса вызывающего.

Метаданные элементов, экспортированных из модуля, имеют свойство ModuleName. Это свойство заполняется именем модуля, в котором они были экспортированы.

> [!WARNING]
> Если имя экспортированного элемента использует неутвержденную команду или если имя члена использует ограниченные символы, то при выполнении командлета [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) отображается предупреждение.

По умолчанию командлет [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) не возвращает ни одного объекта в конвейер. Однако командлет поддерживает параметр **PassThru** , который можно использовать для возврата объекта [System. Management. Automation. PSModuleInfo](/dotnet/api/System.Management.Automation.PSModuleInfo) для каждого импортируемого модуля. Для отправки выходных данных на узел Пользователи должны запустить командлет [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) .

## <a name="restricting--the-members-that-are-imported"></a>Ограничьте импортируемые элементы

При импорте модуля с помощью командлета [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) по умолчанию все экспортированные элементы модуля импортируются в сеанс, включая все команды, экспортированные в модуль вложенным модулем. По умолчанию переменные и псевдонимы не экспортируются. Чтобы ограничить экспортируемые элементы, используйте [манифест модуля](./how-to-write-a-powershell-module-manifest.md).
Чтобы ограничить импортируемые элементы, используйте следующие параметры `Import-Module` командлета.

- **Функция**: этот параметр разрешает экспорт экспортируемых функций. (Если вы используете манифест модуля, см. раздел FunctionsToExport Key.)

- `**Командлет**. Этот параметр позволяет ограничивать экспортируемые командлеты (если вы используете манифест модуля, см. раздел CmdletsToExport).

- **Переменная**. Этот параметр позволяет ограничивать экспортируемые переменные (если используется манифест модуля, см. раздел вариаблестоекспорт).

- **Псевдоним**. Этот параметр позволяет ограничивать экспортируемые псевдонимы (если вы используете манифест модуля, см. раздел алиасестоекспорт).

## <a name="see-also"></a>См. также

[Написание модуля Windows PowerShell](./writing-a-windows-powershell-module.md)
