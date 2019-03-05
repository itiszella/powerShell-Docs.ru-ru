---
title: Параметры безопасности | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e199bba3-90d3-41ca-9d78-cb502e58508d
caps.latest.revision: 6
ms.openlocfilehash: c8b3f907a80d1f6125a5ac04236245503db76ed0
ms.sourcegitcommit: ce46e5098786e19d521b4bf948ff62d2b90bc53e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57251308"
---
# <a name="security-parameters"></a><span data-ttu-id="0f457-102">Параметры безопасности</span><span class="sxs-lookup"><span data-stu-id="0f457-102">Security Parameters</span></span>

<span data-ttu-id="0f457-103">Ниже перечислены рекомендуемые имена и функциональные возможности для параметров, используемых для предоставления сведений о безопасности для операции, такие как параметры, указывающие сведения о сертификате ключа и привилегий.</span><span class="sxs-lookup"><span data-stu-id="0f457-103">The following table lists the recommended names and functionality for parameters used to provide security information for an operation, such as parameters that specify certificate key and privilege information.</span></span>

|<span data-ttu-id="0f457-104">Параметр</span><span class="sxs-lookup"><span data-stu-id="0f457-104">Parameter</span></span>|<span data-ttu-id="0f457-105">Функции</span><span class="sxs-lookup"><span data-stu-id="0f457-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="0f457-106">**СПИСОК УПРАВЛЕНИЯ ДОСТУПОМ**</span><span class="sxs-lookup"><span data-stu-id="0f457-106">**ACL**</span></span><br><span data-ttu-id="0f457-107">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-107">Data type: String</span></span>|<span data-ttu-id="0f457-108">Реализуйте этот параметр для указания уровня управления доступом защиты для каталога или для универсального кода ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="0f457-108">Implement this parameter to specify the access control level of protection for a catalog or for a Uniform Resource Identifier (URI).</span></span>|
|<span data-ttu-id="0f457-109">**CertFile**</span><span class="sxs-lookup"><span data-stu-id="0f457-109">**CertFile**</span></span><br><span data-ttu-id="0f457-110">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-110">Data type: String</span></span>|<span data-ttu-id="0f457-111">Реализуйте этот параметр, таким образом, чтобы пользователь может указать имя файла, содержащего одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="0f457-111">Implement this parameter so that the user can specify the name of a file that contains one of the following:</span></span><br><span data-ttu-id="0f457-112">-Сертификат x.509 в кодировке Base64 или различающееся правил кодирования (DER)</span><span class="sxs-lookup"><span data-stu-id="0f457-112">- A Base64 or Distinguished Encoding Rules (DER) encoded x.509 certificate</span></span><br><span data-ttu-id="0f457-113">-Public Key Cryptography стандартов (PKCS) #12 файл, содержащий по крайней мере один сертификат и ключ</span><span class="sxs-lookup"><span data-stu-id="0f457-113">- A Public Key Cryptography Standards (PKCS) #12 file that contains at least one certificate and key</span></span>|
|<span data-ttu-id="0f457-114">**CertIssuerName**</span><span class="sxs-lookup"><span data-stu-id="0f457-114">**CertIssuerName**</span></span><br><span data-ttu-id="0f457-115">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-115">Data type: String</span></span>|<span data-ttu-id="0f457-116">Реализуйте этот параметр, чтобы пользователь может указать имя издателя сертификата или таким образом, пользователь может указать подстроки.</span><span class="sxs-lookup"><span data-stu-id="0f457-116">Implement this parameter so that the user can specify the name of the issuer of a certificate or so that the user can specify a substring.</span></span>|
|<span data-ttu-id="0f457-117">**CertRequestFile**</span><span class="sxs-lookup"><span data-stu-id="0f457-117">**CertRequestFile**</span></span><br><span data-ttu-id="0f457-118">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-118">Data type: String</span></span>|<span data-ttu-id="0f457-119">Реализуйте этот параметр, чтобы указать имя файла, который содержит запрос на сертификат Base64 или DER-кодировке PKCS #10.</span><span class="sxs-lookup"><span data-stu-id="0f457-119">Implement this parameter to specify the name of a file that contains a Base64 or DER-encoded PKCS #10 certificate request.</span></span>|
|<span data-ttu-id="0f457-120">**CertSerialNumber**</span><span class="sxs-lookup"><span data-stu-id="0f457-120">**CertSerialNumber**</span></span><br><span data-ttu-id="0f457-121">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-121">Data type: String</span></span>|<span data-ttu-id="0f457-122">Реализуйте этот параметр, чтобы указать серийный номер, который был выдан центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="0f457-122">Implement this parameter to specify the serial number that was issued by the certification authority.</span></span>|
|<span data-ttu-id="0f457-123">**CertStoreLocation**</span><span class="sxs-lookup"><span data-stu-id="0f457-123">**CertStoreLocation**</span></span><br><span data-ttu-id="0f457-124">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-124">Data type: String</span></span>|<span data-ttu-id="0f457-125">Реализуйте этот параметр, благодаря которому пользователь может указать расположение хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="0f457-125">Implement this parameter so that the user can specify the location of the certificate store.</span></span> <span data-ttu-id="0f457-126">Расположение — обычно это путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="0f457-126">The location is typically a file path.</span></span>|
|<span data-ttu-id="0f457-127">**CertSubjectName**</span><span class="sxs-lookup"><span data-stu-id="0f457-127">**CertSubjectName**</span></span><br><span data-ttu-id="0f457-128">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-128">Data type: String</span></span>|<span data-ttu-id="0f457-129">Реализуйте этот параметр, чтобы пользователь может указать издателя сертификата или таким образом, пользователь может указать подстроки.</span><span class="sxs-lookup"><span data-stu-id="0f457-129">Implement this parameter so that the user can specify the issuer of a certificate or so that the user can specify a substring.</span></span>|
|<span data-ttu-id="0f457-130">**CertUsage**</span><span class="sxs-lookup"><span data-stu-id="0f457-130">**CertUsage**</span></span><br><span data-ttu-id="0f457-131">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-131">Data type: String</span></span>|<span data-ttu-id="0f457-132">Реализуйте этот параметр, чтобы указать использование ключа или расширенное использование ключа.</span><span class="sxs-lookup"><span data-stu-id="0f457-132">Implement this parameter to specify the key usage or the enhanced key usage.</span></span> <span data-ttu-id="0f457-133">Ключ может быть представлен как немного маски, немного, идентификатор объекта (OID), или строку.</span><span class="sxs-lookup"><span data-stu-id="0f457-133">The key can be represented as a bit mask, a bit, an object identifier (OID), or a string.</span></span>|
|<span data-ttu-id="0f457-134">**Учетные данные**</span><span class="sxs-lookup"><span data-stu-id="0f457-134">**Credential**</span></span><br><span data-ttu-id="0f457-135">Тип данных: [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)</span><span class="sxs-lookup"><span data-stu-id="0f457-135">Data type: [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)</span></span>|<span data-ttu-id="0f457-136">Реализуйте этот параметр, чтобы командлет автоматически пользователю будет предложено ввести имя пользователя или пароль.</span><span class="sxs-lookup"><span data-stu-id="0f457-136">Implement this parameter so that the cmdlet will automatically prompt the user for a user name or password.</span></span> <span data-ttu-id="0f457-137">Текст запроса и отображается в том случае, если полный учетных данных не предоставляется напрямую.</span><span class="sxs-lookup"><span data-stu-id="0f457-137">A prompt for both is displayed if a full credential is not supplied directly.</span></span>|
|<span data-ttu-id="0f457-138">**CSPName**</span><span class="sxs-lookup"><span data-stu-id="0f457-138">**CSPName**</span></span><br><span data-ttu-id="0f457-139">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-139">Data type: String</span></span>|<span data-ttu-id="0f457-140">Реализуйте этот параметр, благодаря которому пользователь может указать имя сертификата поставщика услуг (CSP).</span><span class="sxs-lookup"><span data-stu-id="0f457-140">Implement this parameter so that the user can specify the name of the certificate service provider (CSP).</span></span>|
|<span data-ttu-id="0f457-141">**CSPType**</span><span class="sxs-lookup"><span data-stu-id="0f457-141">**CSPType**</span></span><br><span data-ttu-id="0f457-142">Тип данных: Целое число</span><span class="sxs-lookup"><span data-stu-id="0f457-142">Data type: Integer</span></span>|<span data-ttu-id="0f457-143">Реализуйте этот параметр, благодаря которому пользователь может указать тип CSP.</span><span class="sxs-lookup"><span data-stu-id="0f457-143">Implement this parameter so that the user can specify the type of CSP.</span></span>|
|<span data-ttu-id="0f457-144">**Группа**</span><span class="sxs-lookup"><span data-stu-id="0f457-144">**Group**</span></span><br><span data-ttu-id="0f457-145">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-145">Data type: String</span></span>|<span data-ttu-id="0f457-146">Реализуйте этот параметр, чтобы пользователь может указать коллекцию участников, для доступа.</span><span class="sxs-lookup"><span data-stu-id="0f457-146">Implement this parameter so that the user can specify a collection of principals for access.</span></span> <span data-ttu-id="0f457-147">Дополнительные сведения см. в описании **участника** параметра.</span><span class="sxs-lookup"><span data-stu-id="0f457-147">For more information, see the description of the **Principal** parameter.</span></span>|
|<span data-ttu-id="0f457-148">**KeyAlgorithm**</span><span class="sxs-lookup"><span data-stu-id="0f457-148">**KeyAlgorithm**</span></span><br><span data-ttu-id="0f457-149">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-149">Data type: String</span></span>|<span data-ttu-id="0f457-150">Реализуйте этот параметр, чтобы пользователь может указать алгоритм создания ключа для защиты.</span><span class="sxs-lookup"><span data-stu-id="0f457-150">Implement this parameter so that the user can specify the key generation algorithm to use for security.</span></span>|
|<span data-ttu-id="0f457-151">**КонтейнерКлючей**</span><span class="sxs-lookup"><span data-stu-id="0f457-151">**KeyContainerName**</span></span><br><span data-ttu-id="0f457-152">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-152">Data type: String</span></span>|<span data-ttu-id="0f457-153">Реализуйте этот параметр, благодаря которому пользователь может указать имя контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="0f457-153">Implement this parameter so that the user can specify the name of the key container.</span></span>|
|<span data-ttu-id="0f457-154">**Значение KeyLength**</span><span class="sxs-lookup"><span data-stu-id="0f457-154">**KeyLength**</span></span><br><span data-ttu-id="0f457-155">Тип данных: Целое число</span><span class="sxs-lookup"><span data-stu-id="0f457-155">Data type: Integer</span></span>|<span data-ttu-id="0f457-156">Реализуйте этот параметр, чтобы пользователь может указать длину ключа в битах.</span><span class="sxs-lookup"><span data-stu-id="0f457-156">Implement this parameter so that the user can specify the length of the key in bits.</span></span>|
|<span data-ttu-id="0f457-157">**Операция**</span><span class="sxs-lookup"><span data-stu-id="0f457-157">**Operation**</span></span><br><span data-ttu-id="0f457-158">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-158">Data type: String</span></span>|<span data-ttu-id="0f457-159">Реализуйте этот параметр, чтобы пользователь может указать действие, которое может быть выполнена на защищенных объектов.</span><span class="sxs-lookup"><span data-stu-id="0f457-159">Implement this parameter so that the user can specify an action that can be performed on a protected object.</span></span>|
|<span data-ttu-id="0f457-160">**Основной**</span><span class="sxs-lookup"><span data-stu-id="0f457-160">**Principal**</span></span><br><span data-ttu-id="0f457-161">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-161">Data type: String</span></span>|<span data-ttu-id="0f457-162">Реализуйте этот параметр, таким образом, пользователь может указать уникальную идентифицировать сущность доступа.</span><span class="sxs-lookup"><span data-stu-id="0f457-162">Implement this parameter so that the user can specify a unique identifiable entity for access.</span></span>|
|<span data-ttu-id="0f457-163">**привилегий**</span><span class="sxs-lookup"><span data-stu-id="0f457-163">**Privilege**</span></span><br><span data-ttu-id="0f457-164">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-164">Data type: String</span></span>|<span data-ttu-id="0f457-165">Реализуйте этот параметр, чтобы пользователь может указать справа, командлет необходимо выполнять операции для конкретной сущности.</span><span class="sxs-lookup"><span data-stu-id="0f457-165">Implement this parameter so that the user can specify the right a cmdlet needs to perform an operation for a particular entity.</span></span>|
|<span data-ttu-id="0f457-166">**Привилегии**</span><span class="sxs-lookup"><span data-stu-id="0f457-166">**Privileges**</span></span><br><span data-ttu-id="0f457-167">Тип данных: Массив привилегий</span><span class="sxs-lookup"><span data-stu-id="0f457-167">Data type: Array of privileges</span></span>|<span data-ttu-id="0f457-168">Реализуйте этот параметр, благодаря которому пользователь может указать права, необходимые для выполнения своих операций для определенной записи для командлета.</span><span class="sxs-lookup"><span data-stu-id="0f457-168">Implement this parameter so that the user can specify the rights that a cmdlet needs to perform its operation for a particular entry.</span></span>|
|<span data-ttu-id="0f457-169">**Роли**</span><span class="sxs-lookup"><span data-stu-id="0f457-169">**Role**</span></span><br><span data-ttu-id="0f457-170">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-170">Data type: String</span></span>|<span data-ttu-id="0f457-171">Реализуйте этот параметр, таким образом, пользователь может указать набор операций, которые могут быть выполнены в сущности.</span><span class="sxs-lookup"><span data-stu-id="0f457-171">Implement this parameter so that the user can specify a set of operations that can be performed by an entity.</span></span>|
|<span data-ttu-id="0f457-172">**SaveCred**</span><span class="sxs-lookup"><span data-stu-id="0f457-172">**SaveCred**</span></span><br><span data-ttu-id="0f457-173">Тип данных: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0f457-173">Data type: SwitchParameter</span></span>|<span data-ttu-id="0f457-174">Реализуйте этот параметр, чтобы учетные данные, которые ранее были сохранены с пользователя будет использоваться при указании параметра.</span><span class="sxs-lookup"><span data-stu-id="0f457-174">Implement this parameter so that credentials that were previously saved by the user will be used when the parameter is specified.</span></span>|
|<span data-ttu-id="0f457-175">**Область**</span><span class="sxs-lookup"><span data-stu-id="0f457-175">**Scope**</span></span><br><span data-ttu-id="0f457-176">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-176">Data type: String</span></span>|<span data-ttu-id="0f457-177">Реализуйте этот параметр, чтобы пользователь может указать группы защищаемых объектов для командлета.</span><span class="sxs-lookup"><span data-stu-id="0f457-177">Implement this parameter so that the user can specify the group of protected objects for the cmdlet.</span></span>|
|<span data-ttu-id="0f457-178">**ИД БЕЗОПАСНОСТИ**</span><span class="sxs-lookup"><span data-stu-id="0f457-178">**SID**</span></span><br><span data-ttu-id="0f457-179">Тип данных: Строка</span><span class="sxs-lookup"><span data-stu-id="0f457-179">Data type: String</span></span>|<span data-ttu-id="0f457-180">Реализуйте этот параметр, благодаря которому пользователь может указать уникальный идентификатор, который представляет участника.</span><span class="sxs-lookup"><span data-stu-id="0f457-180">Implement this parameter so that the user can specify a unique identifier that represents a principal.</span></span>|
|<span data-ttu-id="0f457-181">**доверенные**</span><span class="sxs-lookup"><span data-stu-id="0f457-181">**Trusted**</span></span><br><span data-ttu-id="0f457-182">Тип данных: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0f457-182">Data type: SwitchParameter</span></span>|<span data-ttu-id="0f457-183">Реализуйте этот параметр, чтобы уровни доверия поддерживаются в том случае, если этот параметр указан.</span><span class="sxs-lookup"><span data-stu-id="0f457-183">Implement this parameter so that trust levels are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="0f457-184">**trustLevel**</span><span class="sxs-lookup"><span data-stu-id="0f457-184">**TrustLevel**</span></span><br><span data-ttu-id="0f457-185">Тип данных: Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="0f457-185">Data type: Keyword</span></span>|<span data-ttu-id="0f457-186">Реализуйте этот параметр, чтобы пользователь может указать уровень доверия, который поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0f457-186">Implement this parameter so that the user can specify the trust level that is supported.</span></span> <span data-ttu-id="0f457-187">Например возможные значения включают в Интернете, интрасети и полное доверие.</span><span class="sxs-lookup"><span data-stu-id="0f457-187">For example, possible values include internet, intranet, and fulltrust.</span></span>|

## <a name="see-also"></a><span data-ttu-id="0f457-188">См. также</span><span class="sxs-lookup"><span data-stu-id="0f457-188">See Also</span></span>

[<span data-ttu-id="0f457-189">Параметры командлета</span><span class="sxs-lookup"><span data-stu-id="0f457-189">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="0f457-190">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f457-190">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="0f457-191">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f457-191">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)