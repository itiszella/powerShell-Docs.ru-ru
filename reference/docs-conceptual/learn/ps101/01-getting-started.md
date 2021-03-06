---
title: Начало работы с PowerShell
description: Сведения для начинающих пользователей о том, где найти и как запустить PowerShell.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 0f72fb5baf5b829142b18ed774261e9b3b66291b
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438025"
---
# <a name="chapter-1---getting-started-with-powershell"></a>Глава 1. Начало работы с PowerShell

Я часто вижу, что выступающие на конференциях и собраниях групп пользователей уже работают с PowerShell, когда демонстрируют презентации начального уровня. Эта книга начинается с ответов на вопросы, которые задавали участники мероприятий, ранее не использовавшие PowerShell.

В частности, эта глава посвящена поиску и запуску PowerShell, а также решению некоторых первоначальных проблем, с которыми сталкиваются новые пользователи при работе с PowerShell. Обязательно ознакомьтесь с примерами, приведенными в этой главе, и выполните их на компьютере Windows 10 с лабораторной средой.

## <a name="what-do-i-need-to-get-started-with-powershell"></a>Что нужно, чтобы начать работу с PowerShell?

Все современные версии операционных систем Windows поставляются с установленной оболочкой PowerShell. Если вы используете версию, предшествующую 5.1, следует установить последнюю версию.

- Сведения об обновлении до версии PowerShell 5.1 см. в разделе [Обновление существующей версии Windows PowerShell][].
- Сведения об установке последней версии PowerShell см. в статье [Installing Windows PowerShell][].

## <a name="where-do-i-find-powershell"></a>Где найти PowerShell?

Самый простой способ найти PowerShell в Windows 10 — ввести **PowerShell** в строке поиска, как показано на рис. 1-1.

![Рис. 1-1](media/figure1-1.png)

Обратите внимание, что на рис. 1-1 показаны четыре разных ярлыка для PowerShell. Компьютер, используемый в демонстрационных целях в этой книге, работает под управлением 64-разрядной версии Windows 10, поэтому существует 64-разрядная версия консоли PowerShell и PowerShell ISE (интегрированной среды сценариев) и 32-разрядная версия каждой из них (обозначена суффиксом (x86) на ярлыках). Если вы работаете с 32-разрядной версией Windows 10, у вас будет только два ярлыка. У этих элементов нет суффикса (x86), но они являются 32-разрядными версиями. Если у вас установлена 64-разрядная операционная система, рекомендуется запускать 64-разрядную версию PowerShell, только если вас нет особой причины для запуска 32-разрядной версии.

Сведения о запуске PowerShell в других версиях Windows см. в статье [Запуск Windows PowerShell][].

## <a name="how-do-i-launch-powershell"></a>Как запустить PowerShell?

В производственной среде предприятия, которую я поддерживаю, я работаю с тремя разными учетными записями пользователей Active Directory. В лабораторной среде в этой книге используются зеркальные экземпляры этих учетных записей. Я вошел на компьютер с Windows 10 в качестве пользователя домена, который не является администратором домена или локальным администратором.

Я запустил консоль PowerShell, щелкнув ярлык Windows PowerShell, как показано на рис. 1-1.

![Рис. 1-4](media/figure1-4.png)

Обратите внимание, что в строке заголовка консоли PowerShell указано "Windows PowerShell", как показано на рис. 1-4. Некоторые команды выполняются нормально, но PowerShell не поддерживает управление доступом пользователей (UAC). Это означает, что оболочка не может запрашивать повышение прав для задач, требующих утверждения администратором.
Выдается следующее сообщение об ошибке.

```powershell
Get-Service -Name W32Time | Stop-Service
```

```Output
Stop-Service : Service 'Windows Time (W32Time)' cannot be stopped due to the following
error: Cannot open W32Time service on computer '.'.
At line:1 char:29
+ Get-Service -Name W32Time | Stop-Service
+
    + CategoryInfo          : CloseError: (System.ServiceProcess.ServiceController:ServiceController)
     [Stop-Service], ServiceCommandException
    + FullyQualifiedErrorId : CouldNotStopService,Microsoft.PowerShell.Commands.StopServiceCommand
```

Решение этой проблемы заключается в запуске PowerShell от имени пользователя домена, который является локальным администратором.
Именно так настроена моя вторая учетная запись пользователя домена. Согласно принципу наименьших привилегий эта учетная запись НЕ должна быть администратором домена или иметь повышенные привилегии в домене.

Закройте PowerShell. Перезапустите консоль PowerShell, только на этот раз щелкните правой кнопкой мыши ярлык **Windows PowerShell** и выберите пункт **Запуск от имени администратора**, как показано на рис. 1-5.

![Рис. 1-5](media/figure1-5.png)

Если вы выполнили вход в Windows в качестве обычного пользователя, вам будет предложено ввести учетные данные. Я буду вводить учетные данные учетной записи пользователя, которая является пользователем домена и локальным администратором, как показано на рис. 1-6.

![Рис. 1-6](media/figure1-6.png)

После повторного запуска PowerShell с правами администратора в строке заголовка должно быть указано "Администратор: Windows PowerShell", как показано на рис. 1-7.

![Рис. 1-7](media/figure1-7.png)

Теперь, когда PowerShell работает с повышенными привилегиями локального администратора, управление доступом пользователей больше не будет проблемой в случае запуска на локальном компьютере команды, для выполнения которой обычно требуется запрос на повышение прав. Следует иметь в виду, что любая команда, выполняемая из этого экземпляра консоли PowerShell с повышенными привилегиями, также запускается с повышенными привилегиями.

Чтобы упростить поиск PowerShell и запускать оболочку от имени администратора, рекомендуется закрепить ее на панели задач и настроить автоматический запуск от имени администратора при каждом запуске.

Еще раз выполните поиск PowerShell, только на этот раз щелкните ее правой кнопкой мыши и выберите пункт "Закрепить на панели задач", как показано на рис. 1-8.

![Рис. 1-8](media/figure1-8.png)

Щелкните правой кнопкой мыши ярлык PowerShell, который теперь закреплен на панели задач, и выберите пункт "Свойства", как показано на рис. 1-9.

![Рис. 1-9](media/figure1-9.png)

Щелкните "Дополнительно", как показано в первой части рис. 1-10, установите флажок "Запуск от имени администратора", как показано во второй части рис. 1-10, а затем дважды нажмите кнопку OK, чтобы принять изменения и выйти из обоих диалоговых окон.

![Рис. 1-10](media/figure1-10.png)

Вам больше никогда не придется беспокоиться о поиске PowerShell или о том, запущена ли оболочка от имени администратора или нет.

Запуск PowerShell с повышенными привилегиями для предотвращения проблем, связанных с управлением доступом пользователей, влияет только на команды, выполняемые на локальном компьютере. Он не влияет на команды, предназначенные для запуска на удаленных компьютерах.

## <a name="what-version-of-powershell-am-i-running"></a>Какую версию PowerShell я использую?

В PowerShell существует ряд автоматических переменных, в которых хранятся сведения о состоянии. Одной из этих переменных является `$PSVersionTable`, содержащая хэш-таблицу, которую можно использовать для вывода соответствующих сведений о версии PowerShell.

```powershell
$PSVersionTable
```

```Output
Name                           Value
----                           -----
PSVersion                      5.1.19041.1
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
BuildVersion                   10.0.19041.1
CLRVersion                     4.0.30319.42000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

Более новые версии Windows PowerShell распространяются в составе Windows Management Framework (WMF). Конкретная версия .NET Framework зависит от версии WMF. Сведения об обновлении до версии PowerShell 5.1 см. в разделе [Обновление существующей версии Windows PowerShell][].

## <a name="execution-policy"></a>Политика выполнения

Вопреки распространенному мнению, политика выполнения в PowerShell не является средством обеспечения безопасности. Она предназначена для предотвращения непреднамеренного выполнения сценария пользователем. Определенный пользователь может без труда обойти политику выполнения в PowerShell. В таблице 1-2 показана политика выполнения по умолчанию для текущих операционных систем Windows.

| Версия операционной системы Windows | Политика выполнения по умолчанию |
| -------------------------------- | ------------------------ |
| Server 2019                      | Удаленно подписанная            |
| Server 2016                      | Удаленно подписанная            |
| Windows 10                       | С ограниченным доступом               |

Любая команда PowerShell может выполняться в интерактивном режиме, независимо от настройки политики выполнения. Политика выполнения влияет только на команды, выполняемые в сценарии. Командлет `Get-ExecutionPolicy` используется для определения текущего параметра политики выполнения, а командлет `Set-ExecutionPolicy` используется для изменения политики выполнения. Рекомендуется использовать политику **RemoteSigned**, которая требует, чтобы предназначенные для выполнения скачиваемые сценарии были подписаны доверенным издателем.

Проверка текущей политики выполнения

```powershell
Get-ExecutionPolicy
```

```Output
Restricted
```

Если для политики выполнения задано **С ограниченным доступом**, сценарии PowerShell вообще не запускаются. Это параметр по умолчанию для всех клиентских операционных систем Windows. Чтобы продемонстрировать проблему, сохраните следующий код как файл `.ps1` с именем `Stop-TimeService.ps1`.

```powershell
Get-Service -Name W32Time | Stop-Service -PassThru
```

Эта команда выполняется в интерактивном режиме без ошибок при условии, что PowerShell запущена с повышенными правами администратора. Но при сохранении в виде файла сценария и попытке выполнить сценарий выдается ошибка.

```powershell
.\Stop-TimeService.ps1
```

```Output
.\Stop-TimeService.ps1 : File C:\demo\Stop-TimeService.ps1 cannot be loaded because
running scripts is disabled on this system. For more information, see
about_Execution_Policies at http://go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ .\Stop-TimeService.ps1
+
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

Обратите внимание, что в сообщении об ошибке, приведенном в предыдущем наборе результатов, указывается точная проблема (в этой системе отключено выполнение сценариев). При выполнении в PowerShell команды, которая создает сообщение об ошибке, обязательно следует прочесть сообщение об ошибке, а не просто перезапустить команду и надеяться на ее успешное завершение.

Измените политику выполнения PowerShell на удаленно подписанную.

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

```Output
Execution Policy Change
The execution policy helps protect you from scripts that you do not trust. Changing the execution
policy might expose you to the security risks described in the about_Execution_Policies help topic
at http://go.microsoft.com/fwlink/?LinkID=135170. Do you want to change the execution policy?
[Y] Yes [A] Yes to All [N] No [L] No to All [S] Suspend [?] Help (default is "N"):y
```

Обязательно прочтите предупреждение, которое отображается при изменении политики выполнения. Кроме того, рекомендуется ознакомиться с разделом справки [about_Execution_Policies][], чтобы знать о влиянии изменения политики выполнения на безопасность.

Теперь, когда для политики выполнения задано значение **Удаленно подписанная**, сценарий `Stop-TimeService.ps1` будет выполняться без ошибок.

```powershell
.\Stop-TimeService.ps1
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  W32Time            Windows Time
```

Прежде чем продолжить, запустите службу времени Windows. В противном случае могут возникнуть непредвиденные проблемы.

```powershell
Start-Service -Name w32time
```

## <a name="summary"></a>Сводка

В этой главе вы узнали, как найти и запустить PowerShell, а также как создать ярлык для запуска PowerShell от имени администратора. Вы также ознакомились с политикой выполнения по умолчанию и поняли, как ее изменять.

## <a name="review"></a>Просмотр

1. Как определить версию PowerShell, установленную на компьютере?
1. Почему важно запускать PowerShell с повышенными правами администратора?
1. Как определить текущую политику выполнения PowerShell?
1. Чему препятствует политика выполнения PowerShell по умолчанию на клиентских компьютерах Windows?
1. Как изменить политику выполнения PowerShell?

## <a name="recommended-reading"></a>Рекомендуем прочесть

Тем, кто хочет более подробно изучить темы, описанные в этой главе, рекомендуется ознакомиться со следующими разделами справки по PowerShell.

- [about_Automatic_Variables][]
- [about_Execution_Policies][]

В следующей главе вы узнаете о возможности обнаружения команд в PowerShell. Помимо прочих вопросов в ней будет рассматриваться обновление PowerShell, после которого разделы справки можно будет просматривать непосредственно в PowerShell, а не в Интернете.

<!-- link references -->
[about_Automatic_Variables]: /powershell/module/microsoft.powershell.core/about/about_automatic_variables
[about_Execution_Policies]: /powershell//powershell/module/microsoft.powershell.core/about/about_execution_policies
[Обновление существующей версии Windows PowerShell]: /powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell
[Installing Windows PowerShell]: /powershell/scripting/install/installing-powershell (Установка Windows PowerShell)
[Запуск Windows PowerShell]: /powershell/scripting/windows-powershell/starting-windows-powershell
