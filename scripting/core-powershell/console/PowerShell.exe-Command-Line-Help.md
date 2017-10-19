---
ms.date: 2017-06-05
keywords: "powershell,командлет"
title: "Справка по командной строке PowerShell.exe"
ms.assetid: 1ab7b93b-6785-42c6-a1c9-35ff686a958f
ms.openlocfilehash: 9c56f09ac186b0c3a64cce6700740ca1ba6abd06
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2017
---
# <a name="powershellexe-command-line-help"></a><span data-ttu-id="2ad5f-103">Справка по командной строке PowerShell.exe</span><span class="sxs-lookup"><span data-stu-id="2ad5f-103">PowerShell.exe Command-Line Help</span></span>
<span data-ttu-id="2ad5f-104">Запускает сеанс Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-104">Starts a Windows PowerShell session.</span></span> <span data-ttu-id="2ad5f-105">Можно использовать PowerShell.exe для запуска сеанса Windows PowerShell из командной строки другого средства, такого как Cmd.exe, или использовать его в командной строке Windows PowerShell для запуска нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-105">You can use PowerShell.exe to start a Windows PowerShell session from the command line of another tool, such as Cmd.exe, or use it at the Windows PowerShell command line to start a new session.</span></span> <span data-ttu-id="2ad5f-106">Используйте указанные параметры для настройки сеанса.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-106">Use the parameters to customize the session.</span></span>

## <a name="syntax"></a><span data-ttu-id="2ad5f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ad5f-107">Syntax</span></span>

```
PowerShell[.exe]
       [-EncodedCommand <Base64EncodedCommand>]
       [-ExecutionPolicy <ExecutionPolicy>]
       [-InputFormat {Text | XML}] 
       [-Mta]
       [-NoExit]
       [-NoLogo]
       [-NonInteractive] 
       [-NoProfile] 
       [-OutputFormat {Text | XML}] 
       [-PSConsoleFile <FilePath> | -Version <Windows PowerShell version>]
       [-Sta]
       [-WindowStyle <style>]
       [-File <FilePath> [<Args>]]
       [-Command { - | <script-block> [-args <arg-array>]
                     | <string> [<CommandParameters>] } ]

PowerShell[.exe] -Help | -? | /?
```

## <a name="parameters"></a><span data-ttu-id="2ad5f-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ad5f-108">Parameters</span></span>

### <a name="-encodedcommand-base64encodedcommand"></a><span data-ttu-id="2ad5f-109">-EncodedCommand <Base64EncodedCommand></span><span class="sxs-lookup"><span data-stu-id="2ad5f-109">-EncodedCommand <Base64EncodedCommand></span></span>
<span data-ttu-id="2ad5f-110">Принимает строковую версию команды в кодировке Base 64.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-110">Accepts a base-64-encoded string version of a command.</span></span> <span data-ttu-id="2ad5f-111">Используйте этот параметр для отправки в Windows PowerShell команд, требующих сложных кавычек или фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-111">Use this parameter to submit commands to Windows PowerShell that require complex quotation marks or curly braces.</span></span>

### <a name="-executionpolicy-executionpolicy"></a><span data-ttu-id="2ad5f-112">-ExecutionPolicy <ExecutionPolicy></span><span class="sxs-lookup"><span data-stu-id="2ad5f-112">-ExecutionPolicy <ExecutionPolicy></span></span>
<span data-ttu-id="2ad5f-113">Задает политику выполнения по умолчанию для текущего сеанса и сохраняет ее в переменной среды $env:PSExecutionPolicyPreference.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-113">Sets the default execution policy for the current session and saves it in the $env:PSExecutionPolicyPreference environment variable.</span></span> <span data-ttu-id="2ad5f-114">Этот параметр не изменяет политику выполнения Windows PowerShell, заданную в реестре.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-114">This parameter does not change the Windows PowerShell execution policy that is set in the registry.</span></span> <span data-ttu-id="2ad5f-115">Дополнительные сведения о политиках выполнения Windows PowerShell, включая список допустимых значений, см. в статье about_Execution_Policies (http://go.microsoft.com/fwlink/?LinkID=135170).</span><span class="sxs-lookup"><span data-stu-id="2ad5f-115">For information about Windows PowerShell execution policies, including a list of valid values, see about_Execution_Policies (http://go.microsoft.com/fwlink/?LinkID=135170).</span></span>

### <a name="-file-filepath-parameters"></a><span data-ttu-id="2ad5f-116">-File <FilePath> \[<Parameters>]</span><span class="sxs-lookup"><span data-stu-id="2ad5f-116">-File <FilePath> \[<Parameters>]</span></span>
<span data-ttu-id="2ad5f-117">Запускает указанный сценарий в локальной области ("с точкой"), чтобы создаваемые сценарием функции и переменные были доступны в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-117">Runs the specified script in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="2ad5f-118">Введите путь к файлу сценария и любые параметры.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-118">Enter the script file path and any parameters.</span></span> <span data-ttu-id="2ad5f-119">Параметр **File** должен быть последним в команде, поскольку все символы, введенные после параметра **File**, интерпретируются как путь к файлу сценария и следующие за ним параметры сценария.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-119">**File** must be the last parameter in the command, because all characters typed after the **File** parameter name are interpreted as the script file path followed by the script parameters and their values.</span></span>

<span data-ttu-id="2ad5f-120">Параметры сценария и их значения можно включить в значение параметра **File**.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-120">You can include the parameters of a script, and parameter values, in the value of the **File** parameter.</span></span> <span data-ttu-id="2ad5f-121">Пример: `-File .\Get-Script.ps1 -Domain Central`</span><span class="sxs-lookup"><span data-stu-id="2ad5f-121">For example: `-File .\Get-Script.ps1 -Domain Central`</span></span>

<span data-ttu-id="2ad5f-122">Обычно параметры-переключатели сценария включаются или опускаются.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-122">Typically, the switch parameters of a script are either included or omitted.</span></span> <span data-ttu-id="2ad5f-123">Например, приведенная ниже команда использует параметр **All** файла сценария Get-Script.ps1: `-File .\Get-Script.ps1 -All`</span><span class="sxs-lookup"><span data-stu-id="2ad5f-123">For example, the following command uses the **All** parameter of the Get-Script.ps1 script file: `-File .\Get-Script.ps1 -All`</span></span>

<span data-ttu-id="2ad5f-124">В редких случаях может потребоваться указать для параметра-переключателя логическое значение.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-124">In rare cases, you might need to provide a Boolean value for a switch parameter.</span></span> <span data-ttu-id="2ad5f-125">Чтобы сделать это в значении параметра **File**, заключите его имя и значение в фигурные скобки, например: `-File .\Get-Script.ps1 {-All:$False}`</span><span class="sxs-lookup"><span data-stu-id="2ad5f-125">To provide a Boolean value for a switch parameter in the value of the **File** parameter, enclose the parameter name and value in curly braces, such as the following: `-File .\Get-Script.ps1 {-All:$False}`</span></span>

### <a name="-inputformat-text--xml"></a><span data-ttu-id="2ad5f-126">-InputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="2ad5f-126">-InputFormat {Text | XML}</span></span>
<span data-ttu-id="2ad5f-127">Описывает формат данных, отправляемых в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-127">Describes the format of data sent to Windows PowerShell.</span></span> <span data-ttu-id="2ad5f-128">Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).</span><span class="sxs-lookup"><span data-stu-id="2ad5f-128">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-mta"></a><span data-ttu-id="2ad5f-129">-Mta</span><span class="sxs-lookup"><span data-stu-id="2ad5f-129">-Mta</span></span>
<span data-ttu-id="2ad5f-130">Запускает оболочку с использованием многопотокового подразделения.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-130">Starts Windows PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="2ad5f-131">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-131">This parameter is introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="2ad5f-132">В Windows PowerShell 3.0 по умолчанию используется однопотоковое подразделение (STA).</span><span class="sxs-lookup"><span data-stu-id="2ad5f-132">In Windows PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="2ad5f-133">В Windows PowerShell 2.0 по умолчанию используется многопотоковое подразделение (STA).</span><span class="sxs-lookup"><span data-stu-id="2ad5f-133">In Windows PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-noexit"></a><span data-ttu-id="2ad5f-134">-NoExit</span><span class="sxs-lookup"><span data-stu-id="2ad5f-134">-NoExit</span></span>
<span data-ttu-id="2ad5f-135">Не завершает работу после выполнения команд запуска.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-135">Does not exit after running startup commands.</span></span>

### <a name="-nologo"></a><span data-ttu-id="2ad5f-136">-NoLogo</span><span class="sxs-lookup"><span data-stu-id="2ad5f-136">-NoLogo</span></span>
<span data-ttu-id="2ad5f-137">Скрывает баннер авторских прав при запуске программы.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-137">Hides the copyright banner at startup.</span></span>

### <a name="-noninteractive"></a><span data-ttu-id="2ad5f-138">-NonInteractive</span><span class="sxs-lookup"><span data-stu-id="2ad5f-138">-NonInteractive</span></span>
<span data-ttu-id="2ad5f-139">Не предоставляет пользователю интерактивную командную строку.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-139">Does not present an interactive prompt to the user.</span></span>

### <a name="-noprofile"></a><span data-ttu-id="2ad5f-140">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="2ad5f-140">-NoProfile</span></span>
<span data-ttu-id="2ad5f-141">Не загружает профиль Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-141">Does not load the Windows PowerShell profile.</span></span>

### <a name="-outputformat-text--xml"></a><span data-ttu-id="2ad5f-142">-OutputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="2ad5f-142">-OutputFormat {Text | XML}</span></span>
<span data-ttu-id="2ad5f-143">Определяет формат выходных данных Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-143">Determines how output from Windows PowerShell is formatted.</span></span> <span data-ttu-id="2ad5f-144">Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).</span><span class="sxs-lookup"><span data-stu-id="2ad5f-144">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-psconsolefile-filepath"></a><span data-ttu-id="2ad5f-145">-PSConsoleFile <FilePath></span><span class="sxs-lookup"><span data-stu-id="2ad5f-145">-PSConsoleFile <FilePath></span></span>
<span data-ttu-id="2ad5f-146">Загружает указанный файл консоли Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-146">Loads the specified Windows PowerShell console file.</span></span> <span data-ttu-id="2ad5f-147">Введите путь и имя файла консоли.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-147">Enter the path and name of the console file.</span></span> <span data-ttu-id="2ad5f-148">Для создания файла консоли используйте командлет [Export-Console](https://technet.microsoft.com/en-us/library/4bab1c02-9e61-4aaf-9957-11d1934ef4ef) в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-148">To create a console file, use the [Export-Console](https://technet.microsoft.com/en-us/library/4bab1c02-9e61-4aaf-9957-11d1934ef4ef) cmdlet in Windows PowerShell.</span></span>

### <a name="-sta"></a><span data-ttu-id="2ad5f-149">-Sta</span><span class="sxs-lookup"><span data-stu-id="2ad5f-149">-Sta</span></span>
<span data-ttu-id="2ad5f-150">Запускает Windows PowerShell с использованием многопотокового подразделения.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-150">Starts Windows PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="2ad5f-151">В Windows PowerShell 3.0 по умолчанию используется однопотоковое подразделение (STA).</span><span class="sxs-lookup"><span data-stu-id="2ad5f-151">In Windows PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="2ad5f-152">В Windows PowerShell 2.0 по умолчанию используется многопотоковое подразделение (STA).</span><span class="sxs-lookup"><span data-stu-id="2ad5f-152">In Windows PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-version-windows-powershell-version"></a><span data-ttu-id="2ad5f-153">-Version <Windows PowerShell Version></span><span class="sxs-lookup"><span data-stu-id="2ad5f-153">-Version <Windows PowerShell Version></span></span>
<span data-ttu-id="2ad5f-154">Запускает заданную версию Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-154">Starts the specified version of Windows PowerShell.</span></span> <span data-ttu-id="2ad5f-155">Указанная версия должна быть установлена в системе.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-155">The version that you specify must be installed on the system.</span></span> <span data-ttu-id="2ad5f-156">Если на компьютере установлен Windows PowerShell 3.0, допустимыми значениями являются "3.0" и "2.0".</span><span class="sxs-lookup"><span data-stu-id="2ad5f-156">If Windows PowerShell 3.0 is installed on the computer, valid values are "2.0" and "3.0".</span></span> <span data-ttu-id="2ad5f-157">По умолчанию используется значение "3.0".</span><span class="sxs-lookup"><span data-stu-id="2ad5f-157">The default value is "3.0".</span></span>

<span data-ttu-id="2ad5f-158">Если Windows PowerShell 3.0 не установлен, допустимо только значение "2.0".</span><span class="sxs-lookup"><span data-stu-id="2ad5f-158">If Windows PowerShell 3.0 is not installed, the only valid value is "2.0".</span></span> <span data-ttu-id="2ad5f-159">Другие значения игнорируются.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-159">Other values are ignored.</span></span>

<span data-ttu-id="2ad5f-160">Дополнительные сведения см. в разделе "Установка Windows PowerShell" статьи [Начало работы с Windows PowerShell [СТАРЫЙ MSDN]](https://technet.microsoft.com/en-us/library/69555d95-b481-43e1-86e7-b46d68b3e2dd).</span><span class="sxs-lookup"><span data-stu-id="2ad5f-160">For more information, see "Installing Windows PowerShell" in the [Getting Started with Windows PowerShell [OLD MSDN]](https://technet.microsoft.com/en-us/library/69555d95-b481-43e1-86e7-b46d68b3e2dd).</span></span>

### <a name="-windowstyle-window-style"></a><span data-ttu-id="2ad5f-161">-WindowStyle <Window style></span><span class="sxs-lookup"><span data-stu-id="2ad5f-161">-WindowStyle <Window style></span></span>
<span data-ttu-id="2ad5f-162">Задает стиль окна для сеанса.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-162">Sets the window style for the session.</span></span> <span data-ttu-id="2ad5f-163">Допустимые значения: Normal, Minimized, Maximized и Hidden.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-163">Valid values are Normal, Minimized, Maximized and Hidden.</span></span>

### <a name="-command"></a><span data-ttu-id="2ad5f-164">-Command</span><span class="sxs-lookup"><span data-stu-id="2ad5f-164">-Command</span></span>
<span data-ttu-id="2ad5f-165">Выполняет указанные команды (вместе с параметрами) как введенные в командной строке Windows PowerShell и завершает работу, если не указан параметр NoExit.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-165">Executes the specified commands (and any parameters) as though they were typed at the Windows PowerShell command prompt, and then exits, unless the NoExit parameter is specified.</span></span>

<span data-ttu-id="2ad5f-166">Значением Command может быть строка "-".</span><span class="sxs-lookup"><span data-stu-id="2ad5f-166">The value of Command can be "-", a string.</span></span> <span data-ttu-id="2ad5f-167">или блок сценария.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-167">or a script block.</span></span> <span data-ttu-id="2ad5f-168">Если для Command задано значение "-", текст команды считывается из стандартного ввода.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-168">If the value of Command is "-", the command text is read from standard input.</span></span>

<span data-ttu-id="2ad5f-169">Блоки сценариев должны быть заключены в фигурные скобки ({}).</span><span class="sxs-lookup"><span data-stu-id="2ad5f-169">Script blocks must be enclosed in braces ({}).</span></span> <span data-ttu-id="2ad5f-170">Указать блок сценария можно только при использовании PowerShell.exe в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-170">You can specify a script block only when running PowerShell.exe in Windows PowerShell.</span></span> <span data-ttu-id="2ad5f-171">Результаты сценария возвращаются родительской оболочке как десериализованные объекты XML, а не как активные объекты.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-171">The results of the script are returned to the parent shell as deserialized XML objects, not live objects.</span></span>

<span data-ttu-id="2ad5f-172">Если значением Command является строка, параметр **Command** должен быть последним в команде, так как любой знак, введенный после команды, интерпретируется как ее аргумент.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-172">If the value of Command is a string, **Command** must be the last parameter in the command , because any characters typed after the command are interpreted as the command arguments.</span></span>

<span data-ttu-id="2ad5f-173">При написании строки команды Windows PowerShell используйте следующий формат:</span><span class="sxs-lookup"><span data-stu-id="2ad5f-173">To write a string that runs a Windows PowerShell command, use the format:</span></span>

```
"& {<command>}"
```

<span data-ttu-id="2ad5f-174">где кавычки отделяют строку, а оператор вызова (&) запускает выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-174">where the quotation marks indicate a string and the invoke operator (&) causes the command to be executed.</span></span>

### <a name="-help---"></a><span data-ttu-id="2ad5f-175">-Help, -?, /?</span><span class="sxs-lookup"><span data-stu-id="2ad5f-175">-Help, -?, /?</span></span>
<span data-ttu-id="2ad5f-176">Показывает это сообщение.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-176">Shows this message.</span></span> <span data-ttu-id="2ad5f-177">При вводе команды PowerShell.exe в Windows PowerShell добавляйте в начало параметров команды дефис (-), а не косую черту (/).</span><span class="sxs-lookup"><span data-stu-id="2ad5f-177">If you are typing a PowerShell.exe command in Windows PowerShell, prepend the command parameters with a hyphen (-), not a forward slash (/).</span></span> <span data-ttu-id="2ad5f-178">В Cmd.exe можно использовать как дефис, так и косую черту.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-178">You can use either a hyphen or forward slash in Cmd.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="2ad5f-179">Замечание по устранению неполадок. Обратите внимание, что в Windows PowerShell 2.0 запуск некоторых программ в Windows PowerShell завершается ошибкой с кодом LastExitCode 0xc0000142.</span><span class="sxs-lookup"><span data-stu-id="2ad5f-179">Troubleshooting Note: In Windows PowerShell 2.0, starting some programs in the Windows PowerShell console fails with a LastExitCode of 0xc0000142.</span></span>

## <a name="examples"></a><span data-ttu-id="2ad5f-180">ПРИМЕРЫ</span><span class="sxs-lookup"><span data-stu-id="2ad5f-180">EXAMPLES</span></span>

```
PowerShell -PSConsoleFile sqlsnapin.psc1

PowerShell -Version 2.0 -NoLogo -InputFormat text -OutputFormat XML

PowerShell -Command "Get-EventLog -LogName security"

# in an existing PowerShell session that understands the curly braces mean a script block
PowerShell -Command {Get-EventLog -LogName security}

PowerShell -Command "& {Get-EventLog -LogName security}"

# To use the -EncodedCommand parameter:
$command = "dir 'c:\program files' "
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
powershell.exe -encodedCommand $encodedCommand
```
