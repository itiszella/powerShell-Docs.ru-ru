---
title: Преобразователи системных типов расширенного типа
ms.date: 07/09/2020
ms.topic: conceptual
ms.openlocfilehash: f709a64febe68733b79ed8af804714d3f3ddeaac
ms.sourcegitcommit: d26e2237397483c6333abcf4331bd82f2e72b4e3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2020
ms.locfileid: "86217976"
---
# <a name="ets-type-converters"></a>Преобразователи типов ETS

ETS использует два основных типа преобразователей типов при вызове `LanguagePrimitives.ConvertTo(System.Object, System.Type)` метода. При вызове этого метода PowerShell пытается выполнить преобразование типов с помощью стандартных преобразователей языка PowerShell или пользовательского преобразователя. Если PowerShell не может выполнить преобразование, он выдает исключение **псинвалидкастексцептион** .

## <a name="standard-windows-powershell-language-converters"></a>Стандартные конвертеры языка Windows PowerShell

Эти стандартные преобразования проверяются перед любыми пользовательскими преобразованиями и не могут быть переопределены. В следующей таблице перечислены преобразования типов, выполняемые PowerShell при `ConvertTo(System.Object, System.Type)` вызове метода. Имейте в виду, что ссылки на параметры **валуетоконверт** и **resultType** ссылаются на параметры `ConvertTo(System.Object,System.Type)` метода.

| Из (Валуетоконверт) |  В (resultType)  |                                                                               Результаты                                                                               |
| --------------------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| NULL                  | Строковый            | ""                                                                                                                                                                  |
| NULL                  | Char              | '\0'                                                                                                                                                                |
| NULL                  | Числовой           | `0`типа, указанного в параметре **resultType** .                                                                                                          |
| NULL                  | Логический           | Результаты вызова `IsTrue(System.Object)(Null)` метода.                                                                                                        |
| NULL                  | PSObject          | Новый объект типа **PSObject**.                                                                                                                                    |
| NULL                  | Тип, отличный от значения    | Заканчивающ.                                                                                                                                                               |
| NULL                  | Nullable &lt; T&gt; | Заканчивающ.                                                                                                                                                               |
| Производный класс         | Базовый класс        | **valueToConvert**                                                                                                                                                  |
| Кроме              | Void              | **Аутоматионнулл. Value**                                                                                                                                            |
| Кроме              | Строковый            | Вызывает `ToString` механизм.                                                                                                                                         |
| Кроме              | Логический           | `IsTrue(System.Object) (valueToConvert)`                                                                                                                            |
| Кроме              | PSObject          | Результаты вызова `AsPSObject(System.Object) (valueToConvert)` метода.                                                                                         |
| Кроме              | XML-документ      | Преобразует **валуетоконверт** в строку, а затем вызывает конструктор **XmlDocument** .                                                                                      |
| Массив                 | Массив             | Пытается преобразовать каждый элемент массива.                                                                                                                      |
| Одноэлементный             | Массив             | `Array[0]`равно **валуетоконверт** , преобразованному в тип элемента массива.                                                                            |
| IDictionary           | Хэш-таблица        | Результаты вызова Hashtable (Валуетоконверт).                                                                                                                       |
| Строковый                | Char[]            | `valueToConvert.ToCharArray`                                                                                                                                        |
| Строковый                | Регулярные             | Результаты вызова `Regx(valueToConvert)` .                                                                                                                          |
| Строковый                | Тип              | Возвращает соответствующий тип, используя параметр **валуетоконверт** для поиска **рунспацеконфигуратион. assemblies**.                                                 |
| Строка                | Числовой           | Если **валуетоконверт** имеет значение "", возвращает `0` **тип resultType**. В противном случае для получения числового значения используется культура "инвариантный язык и региональные параметры".                       |
| Целое число               | System.Enum       | Преобразует целое число в константу, если целое число определяется перечислением. Если целое число не определено, возникает исключение **псинвалидкастексцептион** . |

## <a name="custom-conversions"></a>Пользовательские преобразования

Если PowerShell не удается преобразовать тип с помощью стандартного преобразователя языка PowerShell, он проверяет наличие пользовательских преобразователей. PowerShell ищет несколько типов пользовательских преобразователей в порядке, описанном в этом разделе. Имейте в виду, что ссылки на параметры **валуетоконверт** и **resultType** ссылаются на параметры `ConvertTo(System.Object, System.Type)` метода. Если пользовательский преобразователь создает исключение, дальнейшая попытка преобразования объекта не выполняется, и это исключение упаковывается в исключение **псинвалидкастексцептион** , которое затем создается.

## <a name="powershell-type-converter"></a>Преобразователь типов PowerShell

Преобразователи типов PowerShell используются для преобразования одного типа или семейства типов, например всех типов, производных от класса **System. Enum** . Чтобы создать преобразователь типов PowerShell, необходимо реализовать класс поведению pstypeconverter и связать эту реализацию с целевым классом. Существует два способа связывания преобразователя типов PowerShell с целевым классом.

- Через файл конфигурации типа
- Применение атрибута **TypeConverterAttribute** к целевому классу

Преобразователи типов PowerShell, производные от абстрактного класса [поведению pstypeconverter](/dotnet/api/system.management.automation.pstypeconverter) , предоставляют методы для преобразования объекта в конкретный тип или из определенного типа. Если параметр **валуетоконверт** содержит объект с соответствующим преобразователем типов PowerShell, то PowerShell вызывает метод`PSTypeConverter.ConvertTo(System.Object, System.Type,System.IFormatProvider, System.Boolean)`
метод связанного преобразователя для преобразования объекта в тип, указанный параметром **resultType** . Если параметр **resultType** ссылается на тип, связанный с преобразователем типов PowerShell, то PowerShell вызывает метод`PSTypeConverter.ConvertFrom(System.Object,System.Type, System.IFormatProvider, System.Boolean)`
метод связанного преобразователя для преобразования объекта из типа, указанного параметром **resultType** .

## <a name="system-type-converter"></a>Преобразователь системных типов

Преобразователи системных типов используются для преобразования определенного целевого класса. Этот тип преобразователя нельзя использовать для преобразования семейства классов. Чтобы создать преобразователь системных типов, необходимо реализовать класс [TypeConverter](/dotnet/api/system.management.automation.runspaces.typedata.typeconverter#System_Management_Automation_Runspaces_TypeData_TypeConverter) и связать эту реализацию с целевым классом. Существует два способа связывания преобразователя системных типов с целевым классом.

- Через файл конфигурации типа
- Применение атрибута TypeConverterAttribute к целевому классу

## <a name="parse-converter"></a>Преобразователь анализа

Если параметр **валуетоконверт** является строкой, а тип объекта параметра **resultType** имеет `Parse` метод, то `Parse` вызывается метод для преобразования строки.

## <a name="constructor-converter"></a>Преобразователь конструктора

Если тип объекта параметра **resultType** имеет конструктор с одним параметром, который имеет тот же тип, что и объект параметра **валуетоконверт** , то вызывается этот конструктор.

## <a name="implicit-cast-operator-converter"></a>Преобразователь операторов явного приведения

Если параметр **валуетоконверт** имеет неявный оператор приведения, который преобразует в **тип resultType**, то вызывается его оператор CAST. Если параметр **resultType** имеет неявный оператор приведения, который выполняет преобразование из **валуетоконверт**, то вызывается его оператор CAST.

## <a name="explicit-cast-operator-converter"></a>Преобразователь операторов явного приведения

Если параметр **валуетоконверт** имеет явный оператор приведения, который преобразует в **resultType**, то вызывается его оператор CAST. Если параметр **resultType** имеет явный оператор приведения, преобразующий из **валуетоконверт**, то вызывается его оператор CAST.