---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Известные проблемы и ограничения настройки требуемого состояния (DSC)
ms.openlocfilehash: 6faf24795d14a93f265943029d9f6f1388f32263
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71147724"
---
# <a name="desired-state-configuration-dsc-known-issues-and-limitations"></a><span data-ttu-id="b4ae2-103">Известные проблемы и ограничения настройки требуемого состояния (DSC)</span><span class="sxs-lookup"><span data-stu-id="b4ae2-103">Desired State Configuration (DSC) Known Issues and Limitations</span></span>

## <a name="breaking-change-certificates-used-to-encryptdecrypt-passwords-in-dsc-configurations-may-not-work-after-installing-wmf-50-rtm"></a><span data-ttu-id="b4ae2-104">Критическое изменение: сертификаты, используемые для шифрования и расшифровки паролей в конфигурациях DSC, могут не работать после установки WMF 5.0 RTM</span><span class="sxs-lookup"><span data-stu-id="b4ae2-104">Breaking Change: Certificates used to encrypt/decrypt passwords in DSC configurations may not work after installing WMF 5.0 RTM</span></span>

<span data-ttu-id="b4ae2-105">В выпусках WMF 4.0 и WMF 5.0 Preview DSC не позволял использовать в конфигурациях пароли длиннее 121 символов.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-105">In WMF 4.0 and WMF 5.0 Preview releases, DSC would not allow passwords in the configuration to be of length more than 121 characters.</span></span> <span data-ttu-id="b4ae2-106">DSC требовал использования коротких паролей даже в тех случаях, когда были нужны длинные и надежные пароли.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-106">DSC was forcing to use short passwords even if lengthy and strong password was desired.</span></span> <span data-ttu-id="b4ae2-107">Это критическое изменение позволяет использовать в конфигурации DSC пароли произвольной длины.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-107">This breaking change allows passwords to be of arbitrary length in the DSC configuration.</span></span>

<span data-ttu-id="b4ae2-108">**Решение** Повторно создайте сертификат с использованием шифрования ключа или данных и расширенного ключа шифрования документов (1.3.6.1.4.1.311.80.1).</span><span class="sxs-lookup"><span data-stu-id="b4ae2-108">**Resolution:** Re-create the certificate with Data Encipherment or Key Encipherment Key usage, and Document Encryption Enhanced Key usage (1.3.6.1.4.1.311.80.1).</span></span> <span data-ttu-id="b4ae2-109">Дополнительные сведения см. в статье [Protect-CmsMessage](/powershell/module/Microsoft.PowerShell.Security/Protect-CmsMessage).</span><span class="sxs-lookup"><span data-stu-id="b4ae2-109">For more information, see [Protect-CmsMessage](/powershell/module/Microsoft.PowerShell.Security/Protect-CmsMessage).</span></span>

## <a name="dsc-cmdlets-may-fail-after-installing-wmf-50-rtm"></a><span data-ttu-id="b4ae2-110">После установки WMF 5.0 RTM может произойти сбой командлетов DSC</span><span class="sxs-lookup"><span data-stu-id="b4ae2-110">DSC cmdlets may fail after installing WMF 5.0 RTM</span></span>

<span data-ttu-id="b4ae2-111">`Start-DscConfiguration` и другие командлеты DSC могут завершаться со сбоем после установки WMF 5.0 RTM, выдавая следующую ошибку:</span><span class="sxs-lookup"><span data-stu-id="b4ae2-111">`Start-DscConfiguration` and other DSC cmdlets may fail after installing WMF 5.0 RTM with the following error:</span></span>

```Output
LCM failed to retrieve the property PendingJobStep from the object of class dscInternalCache .
+ CategoryInfo : ObjectNotFound: (root/Microsoft/...gurationManager:String) [], CimException
+ FullyQualifiedErrorId : MI RESULT 6
+ PSComputerName : localhost
```

<span data-ttu-id="b4ae2-112">**Решение** Удалите DSCEngineCache.mof, выполнив следующую команду в сеансе PowerShell с повышенными правами ("Запуск от имени администратора"):</span><span class="sxs-lookup"><span data-stu-id="b4ae2-112">**Resolution:** Delete DSCEngineCache.mof by running the following command in an elevated PowerShell session (Run as Administrator):</span></span>

```powershell
Remove-Item -Path $env:SystemRoot\system32\Configuration\DSCEngineCache.mof
```

## <a name="dsc-cmdlets-may-not-work-if-wmf-50-rtm-is-installed-on-top-of-wmf-50-production-preview"></a><span data-ttu-id="b4ae2-113">Командлеты DSC могут не работать в случае установки WMF 5.0 RTM поверх WMF 5.0 Production Preview</span><span class="sxs-lookup"><span data-stu-id="b4ae2-113">DSC cmdlets may not work if WMF 5.0 RTM is installed on top of WMF 5.0 Production Preview</span></span>

<span data-ttu-id="b4ae2-114">**Решение** Выполните следующую команду в сеансе PowerShell с повышенными правами ("Запуск от имени администратора"):</span><span class="sxs-lookup"><span data-stu-id="b4ae2-114">**Resolution:** Run the following command in an elevated PowerShell session (run as administrator):</span></span>

```powershell
mofcomp $env:windir\system32\wbem\DscCoreConfProv.mof
```

## <a name="lcm-can-go-into-an-unstable-state-while-using-get-dscconfiguration-in-debugmode"></a><span data-ttu-id="b4ae2-115">LCM может перейти в нестабильное состояние при использовании Get-DscConfiguration в DebugMode</span><span class="sxs-lookup"><span data-stu-id="b4ae2-115">LCM can go into an unstable state while using Get-DscConfiguration in DebugMode</span></span>

<span data-ttu-id="b4ae2-116">Когда LCM находится в режиме DebugMode, нажатие клавиш CTRL+C для остановки обработки `Get-DscConfiguration` может привести к переключению LCM в нестабильное состояние, в котором не работает большинство командлетов DSC.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-116">If LCM is in DebugMode, pressing CTRL+C to stop the processing of `Get-DscConfiguration` can cause LCM to go into an unstable state such that majority of DSC cmdlets won’t work.</span></span>

<span data-ttu-id="b4ae2-117">**Решение** Не нажимайте клавиши CTRL+C во время отладки командлета `Get-DscConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-117">**Resolution:** Don’t press CTRL+C while debugging `Get-DscConfiguration` cmdlet.</span></span>

## <a name="stop-dscconfiguration-may-not-respond-in-debugmode"></a><span data-ttu-id="b4ae2-118">STOP-DscConfiguration может не отвечать в DebugMode</span><span class="sxs-lookup"><span data-stu-id="b4ae2-118">Stop-DscConfiguration may not respond in DebugMode</span></span>

<span data-ttu-id="b4ae2-119">Когда LCM находится в режиме DebugMode, `Stop-DscConfiguration` может не отвечать при попытке остановить операцию, запущенную `Get-DscConfiguration`</span><span class="sxs-lookup"><span data-stu-id="b4ae2-119">If LCM is in DebugMode, `Stop-DscConfiguration` may not respond while trying to stop an operation started by `Get-DscConfiguration`</span></span>

<span data-ttu-id="b4ae2-120">**Решение** Завершите отладку операции, запущенной `Get-DscConfiguration`, как описано в статье [Отладка ресурсов DSC](/powershell/dsc/troubleshooting/debugResource).</span><span class="sxs-lookup"><span data-stu-id="b4ae2-120">**Resolution:** Finish the debugging of the operation started by `Get-DscConfiguration` as outlined in [Debugging DSC resources](/powershell/dsc/troubleshooting/debugResource).</span></span>

## <a name="no-verbose-error-messages-are-shown-in-debugmode"></a><span data-ttu-id="b4ae2-121">В DebugMode не отображаются подробные сообщения об ошибках</span><span class="sxs-lookup"><span data-stu-id="b4ae2-121">No Verbose Error Messages are shown in DebugMode</span></span>

<span data-ttu-id="b4ae2-122">Когда LCM находится в режиме **DebugMode**, не отображаются подробные сообщения об ошибках из ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-122">If LCM is in **DebugMode**, no verbose error messages are displayed from DSC Resources.</span></span>

<span data-ttu-id="b4ae2-123">**Решение** Отключите **DebugMode** для просмотра подробных сообщений из ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-123">**Resolution:** Disable **DebugMode** to see verbose messages from the resource</span></span>

## <a name="invoke-dscresource-operations-cannot-be-retrieved-by-get-dscconfigurationstatus-cmdlet"></a><span data-ttu-id="b4ae2-124">Командлету Get-DscConfigurationStatus не удается получить операции Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="b4ae2-124">Invoke-DscResource operations cannot be retrieved by Get-DscConfigurationStatus cmdlet</span></span>

<span data-ttu-id="b4ae2-125">После использования командлета `Invoke-DscResource` для прямого вызова методов любого ресурса записи такой операции не удается извлечь с помощью `Get-DscConfigurationStatus`.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-125">After using `Invoke-DscResource` cmdlet to directly invoke any resource’s methods, the records of such operation cannot be retrieved through `Get-DscConfigurationStatus`.</span></span>

<span data-ttu-id="b4ae2-126">**Решение** Нет.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-126">**Resolution:** None.</span></span>

## <a name="get-dscconfigurationstatus-returns-pull-cycle-operations-as-type-consistency"></a><span data-ttu-id="b4ae2-127">Get-DscConfigurationStatus возвращает операции цикла извлечения с типом **Consistency**</span><span class="sxs-lookup"><span data-stu-id="b4ae2-127">Get-DscConfigurationStatus returns pull cycle operations as type **Consistency**</span></span>

<span data-ttu-id="b4ae2-128">Когда узел переведен в режим обновления PULL, для каждой выполненной операции извлечения командлет `Get-DscConfigurationStatus` сообщает тип операции, как **Consistency**, а не *Initial*.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-128">When a node is set to PULL refresh mode, for each pull operation performed, `Get-DscConfigurationStatus` cmdlet reports the operation type as **Consistency** instead of *Initial*</span></span>

<span data-ttu-id="b4ae2-129">**Решение** Нет.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-129">**Resolution:** None.</span></span>

## <a name="invoke-dscresource-cmdlet-does-not-return-message-in-the-order-they-were-produced"></a><span data-ttu-id="b4ae2-130">Командлет Invoke-DscResource не возвращает сообщения в том порядке, в котором они были созданы</span><span class="sxs-lookup"><span data-stu-id="b4ae2-130">Invoke-DscResource cmdlet does not return message in the order they were produced</span></span>

<span data-ttu-id="b4ae2-131">Командлет `Invoke-DscResource` не возвращает подробные сообщения, предупреждения и сообщения об ошибках в том порядке, в котором они были созданы LCM или ресурсом DSC.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-131">The `Invoke-DscResource` cmdlet does not return verbose, warning, and error messages in the order they were produced by LCM or the DSC resource.</span></span>

<span data-ttu-id="b4ae2-132">**Решение** Нет.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-132">**Resolution:** None.</span></span>

## <a name="dsc-resources-cannot-be-debugged-easily-when-used-with-invoke-dscresource"></a><span data-ttu-id="b4ae2-133">Невозможна простая отладка ресурсов DSC при использовании Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="b4ae2-133">DSC Resources cannot be debugged easily when used with Invoke-DscResource</span></span>

<span data-ttu-id="b4ae2-134">Когда LCM работает в режиме отладки, командлет `Invoke-DscResource` не предоставляет сведения о пространстве выполнения, к которому нужно подключиться для отладки.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-134">When LCM is running in debug mode, `Invoke-DscResource` cmdlet does not give information about runspace to connect to for debugging.</span></span> <span data-ttu-id="b4ae2-135">Дополнительные сведения см. в разделе [Отладка ресурсов DSC](/powershell/dsc/troubleshooting/debugResource).</span><span class="sxs-lookup"><span data-stu-id="b4ae2-135">For more information, see [Debugging DSC resources](/powershell/dsc/troubleshooting/debugResource).</span></span>

<span data-ttu-id="b4ae2-136">**Решение** Найдите пространство выполнения и подключитесь к нему с помощью командлетов `Get-PSHostProcessInfo`, `Enter-PSHostProcess`, `Get-Runspace` и `Debug-Runspace` для отладки ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-136">**Resolution:** Discover and attach to the runspace using cmdlets `Get-PSHostProcessInfo`, `Enter-PSHostProcess` , `Get-Runspace` and `Debug-Runspace` to debug the DSC resource.</span></span>

```powershell
# Find all the processes hosting PowerShell
Get-PSHostProcessInfo

ProcessName    ProcessId AppDomainName
-----------    --------- -------------
powershell          3932 DefaultAppDomain
powershell_ise      2304 DefaultAppDomain
WmiPrvSE            3396 DscPsPluginWkr_AppDomain

# Enter the process that is hosting DSC engine (WMI process with DscPsPluginWkr_Appdomain)
Enter-PSHostProcess -Id 3396 -AppDomainName DscPsPluginWkr_AppDomain

# Find all the available rusnspaces in that process
Get-Runspace

Id Name       ComputerName Type  State  Availability
-- ----       ------------ ----  -----  ------------
 2 Runspace2  localhost    Local Opened InBreakpoint
 5 RemoteHost localhost    Local Opened Busy

# Debug the runspace that is in **InBreakpoint** availability state
Debug-Runspace -Id 2
```

## <a name="various-partial-configuration-documents-for-same-node-cannot-have-identical-resource-names"></a><span data-ttu-id="b4ae2-137">Различные документы неполной конфигурации для одного узла не могут иметь одинаковые имена ресурсов</span><span class="sxs-lookup"><span data-stu-id="b4ae2-137">Various Partial Configuration documents for same node cannot have identical resource names</span></span>

<span data-ttu-id="b4ae2-138">Идентичные имена ресурсов для нескольких неполных конфигураций, развернутых на одном узле, приводят к ошибке во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-138">For several partial configurations that are deployed onto a single node, identical names of resources cause run time error.</span></span>

<span data-ttu-id="b4ae2-139">**Решение** Используйте разные имена для одинаковых ресурсов в различных неполных конфигурациях.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-139">**Resolution:** Use different names for even same resources in different partial configurations.</span></span>

## <a name="start-dscconfiguration-useexisting-does-not-work-with--credential"></a><span data-ttu-id="b4ae2-140">Start-DscConfiguration –UseExisting не работает с параметром -Credential</span><span class="sxs-lookup"><span data-stu-id="b4ae2-140">Start-DscConfiguration –UseExisting does not work with -Credential</span></span>

<span data-ttu-id="b4ae2-141">При использовании `Start-DscConfiguration` с параметром **UseExisting** параметр **Credential** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-141">When using `Start-DscConfiguration` with **UseExisting** parameter, the **Credential** parameter is ignored.</span></span> <span data-ttu-id="b4ae2-142">DSC использует удостоверение процесса по умолчанию для продолжения операции.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-142">DSC uses default process identity to proceed the operation.</span></span> <span data-ttu-id="b4ae2-143">Это вызывает ошибку, если для продолжения работы на удаленном узле требуются другие учетные данные.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-143">This causes error when a different credential is needed to proceed on remote node.</span></span>

<span data-ttu-id="b4ae2-144">**Решение** Используйте сеанс CIM для удаленных операций DSC:</span><span class="sxs-lookup"><span data-stu-id="b4ae2-144">**Resolution:** Use CIM session for remote DSC operations:</span></span>

```powershell
$session = New-CimSession -ComputerName $node -Credential $credential
Start-DscConfiguration -UseExisting -CimSession $session
```

## <a name="ipv6-addresses-as-node-names-in-dsc-configurations"></a><span data-ttu-id="b4ae2-145">IPv6-адреса в качестве имен узлов в конфигурациях DSC</span><span class="sxs-lookup"><span data-stu-id="b4ae2-145">IPv6 Addresses as Node Names in DSC configurations</span></span>

<span data-ttu-id="b4ae2-146">В этом выпуске не поддерживается использование IPv6-адресов в качестве имен узлов в сценариях конфигурации DSC.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-146">IPv6 addresses as node names in DSC configuration scripts are not supported in this release.</span></span>

<span data-ttu-id="b4ae2-147">**Решение** Нет.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-147">**Resolution:** None.</span></span>

## <a name="debugging-of-class-based-dsc-resources"></a><span data-ttu-id="b4ae2-148">Отладка ресурсов DSC `Class-Based`</span><span class="sxs-lookup"><span data-stu-id="b4ae2-148">Debugging of `Class-Based` DSC Resources</span></span>

<span data-ttu-id="b4ae2-149">В этом выпуске отладка ресурсов DSC на основе классов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-149">Debugging of class-based DSC Resources is not supported in this release.</span></span>

<span data-ttu-id="b4ae2-150">**Решение** Нет.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-150">**Resolution:** None.</span></span>

## <a name="variables-and-functions-defined-in-script-scope-in-dsc-class-based-resource-are-not-preserved-across-multiple-calls-to-a-dsc-resource"></a><span data-ttu-id="b4ae2-151">Переменные и функции, определенные в области $script, основанной на классе ресурса DSC, не сохраняются между несколькими вызовами ресурса DSC</span><span class="sxs-lookup"><span data-stu-id="b4ae2-151">Variables and functions defined in $script scope in DSC Class-Based Resource are not preserved across multiple calls to a DSC Resource</span></span>

<span data-ttu-id="b4ae2-152">Несколько последовательных вызовов `Start-DSCConfiguration` завершаются ошибкой, если конфигурация использует любой ресурс на основе класса, у которого переменные или функции определены в области `$script`.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-152">Multiple consecutive calls to `Start-DSCConfiguration` fails if the configuration is using any class-based resource which has variables or functions defined in `$script` scope.</span></span>

<span data-ttu-id="b4ae2-153">**Решение** Определите все переменные и функции в самом классе ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-153">**Resolution:** Define all variables and functions in DSC Resource class itself.</span></span> <span data-ttu-id="b4ae2-154">Переменных и функций области `$script` быть не должно.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-154">No `$script` scope variables/functions.</span></span>

## <a name="dsc-resource-debugging-when-a-resource-is-using-psdscrunascredential"></a><span data-ttu-id="b4ae2-155">Отладка ресурсов DSC, когда ресурс использует PSDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="b4ae2-155">DSC Resource Debugging when a resource is using PSDscRunAsCredential</span></span>

<span data-ttu-id="b4ae2-156">В этом выпуске отладка ресурсов DSC, когда ресурс использует свойство **PSDscRunAsCredential** в конфигурации, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-156">DSC Resource debugging when a resource is using the **PSDscRunAsCredential** property in the configuration is not supported in this release.</span></span>

<span data-ttu-id="b4ae2-157">**Решение** Нет.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-157">**Resolution:** None.</span></span>

## <a name="psdscrunascredential-is-not-supported-for-dsc-composite-resources"></a><span data-ttu-id="b4ae2-158">PsDscRunAsCredential не поддерживается для составных ресурсов DSC</span><span class="sxs-lookup"><span data-stu-id="b4ae2-158">PsDscRunAsCredential is not supported for DSC Composite Resources</span></span>

<span data-ttu-id="b4ae2-159">**Решение** Используйте свойство Credential, если оно доступно.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-159">**Resolution:** Use Credential property if available.</span></span> <span data-ttu-id="b4ae2-160">Например, ServiceSet и WindowsFeatureSet.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-160">Example ServiceSet and WindowsFeatureSet</span></span>

## <a name="get-dscresource--syntax-does-not-reflect-psdscrunascredential-correctly"></a><span data-ttu-id="b4ae2-161">Get-DscResource -Syntax неправильно отражает PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="b4ae2-161">Get-DscResource -Syntax does not reflect PsDscRunAsCredential correctly</span></span>

<span data-ttu-id="b4ae2-162">Параметр **Synta** отражает **PsDscRunAsCredential** неправильно, когда ресурс помечает его как обязательный или не поддерживает его.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-162">The **Syntax** parameter does not reflect **PsDscRunAsCredential** correctly when resource marks it as mandatory or does not support it.</span></span>

<span data-ttu-id="b4ae2-163">**Решение** Нет.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-163">**Resolution:** None.</span></span> <span data-ttu-id="b4ae2-164">Однако создание конфигурации в интегрированной среде сценариев отражает правильные метаданные о свойстве **PsDscRunAsCredential** при использовании технологии IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-164">However, authoring configuration in ISE reflects correct metadata about **PsDscRunAsCredential** property when using IntelliSense.</span></span>

## <a name="windowsoptionalfeature-is-not-available-in-windows-7"></a><span data-ttu-id="b4ae2-165">WindowsOptionalFeature недоступен в Windows 7</span><span class="sxs-lookup"><span data-stu-id="b4ae2-165">WindowsOptionalFeature is not available in Windows 7</span></span>

<span data-ttu-id="b4ae2-166">Ресурс DSC **WindowsOptionalFeature** недоступен в Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-166">The **WindowsOptionalFeature** DSC resource is not available in Windows 7.</span></span> <span data-ttu-id="b4ae2-167">Он требует наличия модуля и командлетов DISM, которые доступны только в Windows 8 и более поздних выпусках.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-167">This resource requires the DISM module, and DISM cmdlets that are available starting in Windows 8 and newer releases of the Windows operating system.</span></span>

## <a name="for-class-based-dsc-resources-import-dscresource--moduleversion-may-not-work-as-expected"></a><span data-ttu-id="b4ae2-168">Для ресурсов DSC на основе классов командлет Import-DscResource -ModuleVersion может не работать, как ожидалось</span><span class="sxs-lookup"><span data-stu-id="b4ae2-168">For Class-based DSC resources, Import-DscResource -ModuleVersion may not work as expected</span></span>

<span data-ttu-id="b4ae2-169">Если у узла компиляции несколько версий модуля ресурса DSC на основе класса, `Import-DscResource -ModuleVersion` не может получить указанную версию и вызывает следующую ошибку компиляции.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-169">If the compilation node has multiple versions of a class-based DSC resource module, `Import-DscResource -ModuleVersion` does not pick the specified version and results in following compilation error.</span></span>

```Output
ImportClassResourcesFromModule : Exception calling "ImportClassResourcesFromModule" with "3" argument(s):
 "Keyword 'MyTestResource' already defined in the configuration."
At C:\Windows\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateConfiguration\PSDesiredStateConfiguration.psm1:2035 char:35
+ ... rcesFound = ImportClassResourcesFromModule -Module $mod -Resources $r ...
+                 ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [ImportClassResourcesFromModule], MethodInvocationException
    + FullyQualifiedErrorId : PSInvalidOperationException,ImportClassResourcesFromModule
```

<span data-ttu-id="b4ae2-170">**Решение** Импортируйте требуемую версию, определив объект **ModuleSpecification** параметра **ModuleName** с ключом **RequiredVersion**, указанным следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b4ae2-170">**Resolution:** Import the required version by defining the **ModuleSpecification** object to the **ModuleName** parameter with **RequiredVersion** key specified as follows:</span></span>

```powershell
Import-DscResource -ModuleName @{ModuleName='MyModuleName';RequiredVersion='1.2'}
```

## <a name="some-dsc-resources-like-registry-resource-may-start-to-take-a-long-time-to-process-the-request"></a><span data-ttu-id="b4ae2-171">Для обработки запросов некоторым ресурсам DSC, например ресурсу реестра, может требоваться много времени.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-171">Some DSC resources like registry resource may start to take a long time to process the request.</span></span>

<span data-ttu-id="b4ae2-172">**Решение 1**: Создайте запланированную задачу, которая периодически очищает папку.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-172">**Resolution 1:** Create a schedule task that cleans up the following folder periodically.</span></span>

```powershell
$env:windir\system32\config\systemprofile\AppData\Local\Microsoft\Windows\PowerShell\CommandAnalysis
```

<span data-ttu-id="b4ae2-173">**Решение 2**: Измените конфигурацию DSC так, чтобы очистка папки *CommandAnalysis* выполнялась в конце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b4ae2-173">**Resolution 2:** Change the DSC configuration to clean up the *CommandAnalysis* folder at the end of the configuration.</span></span>

```powershell
Configuration $configName
{

   # User Data
    Registry SetRegisteredOwner
    {
        Ensure = 'Present'
        Force = $True
        Key = $Node.RegisteredKey
        ValueName = $Node.RegisteredOwnerValue
        ValueType = 'String'
        ValueData = $Node.RegisteredOwnerData
    }
    #
    # Script to delete the config
    #
    script DeleteCommandAnalysisCache
    {
        DependsOn = "[Registry]SetRegisteredOwner"
        getscript = "@{}"
        testscript = 'Remove-Item -Path $env:windir\system32\config\systemprofile\AppData\Local\Microsoft\Windows\PowerShell\CommandAnalysis -Force -Recurse -ErrorAction SilentlyContinue -ErrorVariable ev | out-null;$true'
        setscript = '$true'
    }
}
```