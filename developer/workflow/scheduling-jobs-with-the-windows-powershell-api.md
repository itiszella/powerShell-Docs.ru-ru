---
title: Планирование заданий с помощью Windows PowerShell API | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64718f8e-de60-4fb7-894d-2975b5257ff6
caps.latest.revision: 4
ms.openlocfilehash: ecc0c5c817074782b6c796b24af98639e493880c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853090"
---
# <a name="scheduling-jobs-with-the-powershell-api"></a><span data-ttu-id="0b9d3-102">Планирование заданий с помощью PowerShell API</span><span class="sxs-lookup"><span data-stu-id="0b9d3-102">Scheduling jobs with the PowerShell API</span></span>

<span data-ttu-id="0b9d3-103">Вы можете использовать объекты, предоставляемые **Microsoft.PowerShell.ScheduledJob** пространство имен для следующих целей:</span><span class="sxs-lookup"><span data-stu-id="0b9d3-103">You can use the objects exposed by the **Microsoft.PowerShell.ScheduledJob** namespace to do the following:</span></span>

- <span data-ttu-id="0b9d3-104">Создание запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-104">Create a scheduled job.</span></span>
- <span data-ttu-id="0b9d3-105">Определите, когда выполняется задание.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-105">Define when the job runs.</span></span>
- <span data-ttu-id="0b9d3-106">Получение результатов о завершенном задании.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-106">Get results about the completed job.</span></span>

## <a name="triggering-the-job"></a><span data-ttu-id="0b9d3-107">Активация задания</span><span class="sxs-lookup"><span data-stu-id="0b9d3-107">Triggering the job</span></span>

<span data-ttu-id="0b9d3-108">Первым шагом создания запланированного задания указывается в том случае, если задание должно запускаться.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-108">The first step in creating a scheduled job is specifying when the job should run.</span></span> <span data-ttu-id="0b9d3-109">Это можно сделать, создав и настроив **Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger** объекта.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-109">Do this by creating and configuring a **Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger** object.</span></span> <span data-ttu-id="0b9d3-110">Следующий код создает триггер, которая позволяет запланировать выполнение задания один раз в будущем 20 секунд.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-110">The following code creates a trigger that schedules a job to run a single time 20 seconds in the future.</span></span>

```csharp
ScheduledJobTrigger jobTrigger = ScheduledJobTrigger.CreateOnceTrigger(
                    DateTime.Now.AddSeconds(20), // Create trigger to start job in 20 seconds.
                    TimeSpan.Zero,               // No random delay
                    null,                        // No repetition interval time
                    null,                        // No repetition interval duration
                    1,                           // Trigger Id
                    true);                       // Create trigger enabled

```

## <a name="defining-the-job"></a><span data-ttu-id="0b9d3-111">Определение задания</span><span class="sxs-lookup"><span data-stu-id="0b9d3-111">Defining the job</span></span>

<span data-ttu-id="0b9d3-112">Задание PowerShell определяется путем создания словаря параметров.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-112">You define a PowerShell job by creating a parameter dictionary.</span></span> <span data-ttu-id="0b9d3-113">Поддерживаются следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="0b9d3-113">The following parameters are supported:</span></span>

|<span data-ttu-id="0b9d3-114">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="0b9d3-114">Parameter Name</span></span>|<span data-ttu-id="0b9d3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0b9d3-115">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="0b9d3-116">**Name**</span><span class="sxs-lookup"><span data-stu-id="0b9d3-116">**Name**</span></span>|<span data-ttu-id="0b9d3-117">Имя задания.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-117">The name of the job.</span></span>|
|<span data-ttu-id="0b9d3-118">**ScriptBock**</span><span class="sxs-lookup"><span data-stu-id="0b9d3-118">**ScriptBock**</span></span>|<span data-ttu-id="0b9d3-119">Блок скрипта PowerShell, который указывает, что выполняет задание.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-119">A PowerShell script block that specifies what the job does.</span></span>|
|<span data-ttu-id="0b9d3-120">**FilePath**</span><span class="sxs-lookup"><span data-stu-id="0b9d3-120">**FilePath**</span></span>|<span data-ttu-id="0b9d3-121">Путь к файлу, который содержит блок сценария PowerShell, чтобы указать, что выполняет задание.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-121">Path to a file that contains a PowerShell script block to specify what the job does.</span></span>|
|<span data-ttu-id="0b9d3-122">**InitializationScript**</span><span class="sxs-lookup"><span data-stu-id="0b9d3-122">**InitializationScript**</span></span>|<span data-ttu-id="0b9d3-123">Блок скрипта PowerShell, который инициализирует задания.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-123">A PowerShell script block that initializes the job.</span></span>|
|<span data-ttu-id="0b9d3-124">**ArgumentList**</span><span class="sxs-lookup"><span data-stu-id="0b9d3-124">**ArgumentList**</span></span>|<span data-ttu-id="0b9d3-125">Массив объектов, указывающих аргументы, которые принимает задания.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-125">An array of objects that specify arguments that the job takes.</span></span>|
|<span data-ttu-id="0b9d3-126">**RunAs32**</span><span class="sxs-lookup"><span data-stu-id="0b9d3-126">**RunAs32**</span></span>|<span data-ttu-id="0b9d3-127">Логическое значение, указывающее, следует ли выполнять задание в 32-разрядном процессе.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-127">A boolean value that specifies whether to run the job in a 32-bit process.</span></span>|

<span data-ttu-id="0b9d3-128">В следующем коде создается объект словаря параметров и задает **имя** и **ScriptBlock** параметров.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-128">The following code creates a parameter dictionary object and sets the **Name** and **ScriptBlock** parameters.</span></span>

```csharp
string schedJobDefName = "MySampleSchedJob";
  Dictionary<string, object> jobDefParameters = new Dictionary<string, object>();
  jobDefParameters.Add("Name", schedJobDefName);      // Unique name is required.

  ScriptBlock scriptBlock = ScriptBlock.Create(@"1..5 | foreach {sleep 1; ""SchedJobOutput $_""}");
  jobDefParameters.Add("ScriptBlock", scriptBlock);  // A scriptblock or script FilePath
                                                    // is required.

```

## <a name="creating-the-invocation-and-job-definition-objects"></a><span data-ttu-id="0b9d3-129">Создание вызов, а также задания определения объектов</span><span class="sxs-lookup"><span data-stu-id="0b9d3-129">Creating the invocation and job definition objects</span></span>

<span data-ttu-id="0b9d3-130">Затем создайте `ScheduledJobInvocationInfo` и `ScheduledJobDefinition` объектов, чтобы запустить задание, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0b9d3-130">You then create `ScheduledJobInvocationInfo` and `ScheduledJobDefinition` objects to run the job as shown in the following example:</span></span>

```csharp
ScheduledJobInvocationInfo jobInvocationInfo = new ScheduledJobInvocationInfo(
    new JobDefinition(typeof(ScheduledJobSourceAdapter), scriptBlock.ToString(), schedJobDefName),
    jobDefParameters);

    schedJobDefinition = new ScheduledJobDefinition(
    jobInvocationInfo,                          // Defines the PowerShell job to run.
    new ScheduledJobTrigger[1] { jobTrigger },  // Defines when to run the PowerShell job.
    null,                                       // No custom options. We accept default.
    null);                                      // No credentials. PowerShell job is run
                                                // in default Task Scheduler process, account.

```

## <a name="registering-the-job-with-the-task-scheduler"></a><span data-ttu-id="0b9d3-131">Регистрация задания с планировщиком задач</span><span class="sxs-lookup"><span data-stu-id="0b9d3-131">Registering the job with the task scheduler</span></span>

<span data-ttu-id="0b9d3-132">Следующий код регистрирует задание с [планировщик задач Windows](http://go.microsoft.com/fwlink/?LinkId=251817).</span><span class="sxs-lookup"><span data-stu-id="0b9d3-132">The following code registers the job with the [Windows Task Scheduler](http://go.microsoft.com/fwlink/?LinkId=251817).</span></span>

```csharp
schedJobDefinition.Register();
    registrationSucceeded = true;
    Console.WriteLine("Scheduled job is registered. Waiting 30 seconds for it to run.");

```

## <a name="complete-code-example"></a><span data-ttu-id="0b9d3-133">Полный код примера</span><span class="sxs-lookup"><span data-stu-id="0b9d3-133">Complete code Example</span></span>

<span data-ttu-id="0b9d3-134">Ниже приведен полный пример, из которого были выполнены предыдущие фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="0b9d3-134">The following is the complete code example from which the previous snippets were taken.</span></span>

```csharp
using System;
using System.Threading;
using System.Collections.Generic;
using System.Management.Automation;             // PowerShell namespace.
using Microsoft.PowerShell.ScheduledJob;        // PowerShell ScheduledJob namespace.

namespace Microsoft.Samples.PowerShell.ScheduledJob
{
    /// <summary>
    /// This class contains the Main entry point for the application.
    /// </summary>
    public class ScheduledJobSample
    {
        /// <summary>
        /// This sample shows how to use the PowerShell ScheduledJob API to create
        /// a simple PowerShell scheduled job, register it with a trigger object
        /// that defines when the job will run and retrieve job run results from
        /// the job file store.
        /// </summary>
        /// <param name="args"></param>
        public static void Main(string[] args)
        {
            // ScheduledJobDefinition contains all elements of a PowerShell scheduled
            // job including the PowerShell job script or script file path, scheduling
            // triggers, and scheduling options.
            ScheduledJobDefinition schedJobDefinition = null;
            bool registrationSucceeded = false;

            try
            {
                // First create a scheduled job trigger object.  This object will
                // define when the PowerShell job is scheduled to run.  For this
                // example we will create a trigger to run the job just one time
                // 20 seconds after the trigger object is created.
                // Note: If you are stepping through this code in a debugger you
                // may want to increase the 20 seconds value so that the trigger time
                // remains in the future once you register the scheduled job.
                ScheduledJobTrigger jobTrigger = ScheduledJobTrigger.CreateOnceTrigger(
                    DateTime.Now.AddSeconds(20),      // Create trigger to start job in 20 seconds.
                    TimeSpan.Zero,                    // No random delay
                    null,                             // No repetition interval time
                    null,                             // No repetition interval duration
                    1,                                // Trigger Id
                    true);                            // Create trigger enabled

                // Create a parameter dictionary that defines the PowerShell job.
                // For this example we will create a simple script that runs for
                // 5 seconds generating output.
                // Here are the parameters supported to define the PowerShell job.
                // Name                 - Job name string.
                // ScriptBlock          - PowerShell ScriptBlock type.
                // FilePath             - PowerShell script file path string.
                // InitializationScript - PowerShell Scriptblock type.
                // ArgumentList         - object[] type.
                // RunAs32              - Switch (boolean type).
                string schedJobDefName = "MySampleSchedJob";
                Dictionary<string, object> jobDefParameters = new Dictionary<string, object>();
                jobDefParameters.Add("Name", schedJobDefName);      // Unique name is required.

                ScriptBlock scriptBlock = ScriptBlock.Create(@"1..5 | foreach {sleep 1; ""SchedJobOutput $_""}");
                jobDefParameters.Add("ScriptBlock", scriptBlock);  // A scriptblock or script FilePath is required.

                // Now create a JobInvocation object that contains all information about the PowerShell job to run.
                ScheduledJobInvocationInfo jobInvocationInfo = new ScheduledJobInvocationInfo(
                    new JobDefinition(typeof(ScheduledJobSourceAdapter), scriptBlock.ToString(), schedJobDefName),
                    jobDefParameters);

                // Finally create the scheduled job definition object that pulls all
                // of this information together.
                schedJobDefinition = new ScheduledJobDefinition(
                   jobInvocationInfo,                          // Defines the PowerShell job to run.
                   new ScheduledJobTrigger[1] { jobTrigger },  // Defines when to run the job.
                   null,                                       // No custom options. Accept default.
                   null);                                      // No credentials. PowerShell job is
                                                               // run in default Task Scheduler
                                                               // process, account.

                // Next we register this scheduled job object with Windows Task Scheduler.
                // The Task Scheduler runs the PowerShell script based on the provided job trigger.
                schedJobDefinition.Register();
                registrationSucceeded = true;
                Console.WriteLine("Scheduled job is registered. Waiting 30 seconds for it to run.");

                // You can see this PowerShell job task registered in the Task Scheduler UI.
                // Look under path:
                // Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs

                // Wait for Task Scheduler to run the PowerShell job.
                // This should happen in 20 seconds and then the job takes about 5 seconds to run.
                // If PowerShell job task doesn't run try increasing the trigger time in the
                // ScheduledJobTrigger object. 
                // You can run this task manually from the Task Scheduler UI.
                for (int count = 1; count < 31; ++count)
                {
                    Thread.Sleep(1000);
                    Console.WriteLine(count + " seconds elapsed");
                }

                Console.WriteLine();
                Console.WriteLine("Job run results.");
                Console.WriteLine();

                // Since the PowerShell job runs in a non-interactive Task Scheduler
                // process the job status and output data is written to a file based
                // job store and the directory location is the current user local app
                // data ($env:LOCALAPPDATA).
                // This job store can be accessed through the ScheduledJobSourceAdapter class.
                ScheduledJobSourceAdapter schedJobSourceAdpater = new ScheduledJobSourceAdapter();
                IList<Job2> jobRuns = schedJobSourceAdpater.GetJobs();
                foreach (var jobRun in jobRuns)
                {
                    // Check for jobs in finished state.
                    // Note that job data is not written to the job store until the job
                    // has reached a finished state.
                    JobState jobState = jobRun.JobStateInfo.State;
                    if (jobState == JobState.Completed ||
                        jobState == JobState.Stopped ||
                        jobState == JobState.Failed)
                    {
                        // Write job run finished state.
                        Console.WriteLine("Job Status: " + jobRun.JobStateInfo.State);
                        Console.WriteLine();
                        Console.WriteLine("Job Data");

                        // Write output data.
                        foreach (var item in jobRun.Output)
                        {
                            Console.WriteLine(item.ToString());
                        }

                        // Write any errors.
                        foreach (var item in jobRun.Error)
                        {
                            Console.WriteLine(item.ToString());
                        }
                    }
                }

                Console.WriteLine();
                Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
            catch (ScheduledJobException e)
            {
                Console.WriteLine("Error: " + e.Message);
            }
            finally
            {
                // Unregister this scheduled job or an error will be thrown when
                // running this sample code again (scheduled job already exists.)
                // because all registered scheduled jobs must have a unique name.
                if (registrationSucceeded)
                {
                    schedJobDefinition.Remove(true);
                }
            }
        }
    }
}

```