---
title: Параметры действия | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e4e0cf6-19e0-44b8-8b40-d6f6075276cf
caps.latest.revision: 5
ms.openlocfilehash: 489d8bcdabe904d6a3d2bc6cdb9d7e23d09cbef2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364643"
---
# <a name="activity-parameters"></a>Параметры действий

В следующей таблице перечислены рекомендуемые имена и функциональные возможности для параметров действий.

|Параметр|Функция|
|---|---|
|**Добавление**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы пользователь мог добавлять содержимое в конец ресурса, если указан параметр.|
|**CaseSensitive**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы пользователь мог запрашивать чувствительность к регистру, если указан параметр.|
|**Кнопки**<br>Тип данных: строка|Реализуйте этот параметр, чтобы пользователь мог указать командную строку для выполнения.|
|**компатиблеверсион**<br>Тип данных: объект System. Version|Реализуйте этот параметр, чтобы пользователь мог указать семантику, с которой командлет должен быть совместим с для совместимости с предыдущими версиями.|
|**Повторно**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы при указании параметра использовалось сжатие данных.|
|**Повторно**<br>Тип данных: ключевое слово|Реализуйте этот параметр, чтобы пользователь мог указать алгоритм, используемый для сжатия данных.|
|**Обеспечения**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы данные обрабатывались до тех пор, пока пользователь не завершит командлет при указании параметра. Если параметр не указан, командлет обрабатывает предопределенный объем данных, а затем завершает операцию.|
|**Создания**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы указать, что ресурс создается, если он еще не существует при указании параметра.|
|**Удален**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы ресурсы удалялись, когда командлет завершает свою операцию, если указан параметр.|
|**Значительно**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы указать, что необработанные рабочие элементы обрабатываются до того, как командлет обработает новые данные при указании параметра. Если параметр не указан, рабочие элементы немедленно обрабатываются.|
|**Резин**<br>Тип данных: Int32|Реализуйте этот параметр, чтобы пользователь мог указать, сколько раз ресурс удаляется перед удалением.|
|**ErrorLevel**<br>Тип данных: Int32|Реализуйте этот параметр, чтобы пользователь мог указать уровень ошибок для отчета.|
|**Запрет**<br>Тип данных: String []|Реализуйте этот параметр, чтобы пользователь мог исключить что-либо из действия. Дополнительные сведения об использовании фильтров входных данных см. в разделе [параметры входного фильтра](input-filter-parameters.md).|
|**Фильтрация**<br>Тип данных: ключевое слово|Реализуйте этот параметр, чтобы пользователь мог указать фильтр, выбирающий ресурсы, для которых необходимо выполнить действие командлета. Дополнительные сведения об использовании фильтров входных данных см. в разделе [параметры входного фильтра](./input-filter-parameters.md).|
|**Держивать**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы отслеживать ход выполнения при указании параметра.|
|**Перевести**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы указать, что пользователь может выполнить действие, даже если при указании параметра были обнаружены ограничения. Параметр не допускает компрометации безопасности. Например, этот параметр позволяет пользователю перезаписать файл, доступный только для чтения.|
|**Относится**<br>Тип данных: String []|Реализуйте этот параметр, чтобы пользователь мог включить что-либо в действие. Дополнительные сведения об использовании фильтров входных данных см. в разделе [параметры входного фильтра](input-filter-parameters.md).|
|**Присоединен**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы указать, что обработка выполняется постепенно, если указан параметр. Например, этот параметр позволяет пользователю выполнять добавочное резервное копирование с резервным копированием файлов только с момента последнего резервного копирования.|
|**InputObject**<br>Тип данных: объект|Реализуйте этот параметр, когда командлет принимает входные данные из других командлетов. При определении параметра **InputObject** всегда указывайте ключевое слово **валуефромпипелине** при объявлении атрибута **Parameter** . Дополнительные сведения об использовании фильтров входных данных см. в разделе [параметры входного фильтра](./input-filter-parameters.md).|
|**Вставляет**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы командлет вставил элемент при указании параметра.|
|**Интерактивный**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы командлет работал в интерактивном режиме с пользователем, если указан параметр.|
|**Пределах**<br>Тип данных: хэш-таблица|Реализуйте этот параметр, чтобы пользователь мог указать хэш-таблицу ключевых слов, содержащих значения. В следующем примере показаны образцы значений для параметра **Interval** : `-interval @{ResumeScan=15; Retry=3}`.|
|**Log**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы выполнить аудит действий командлета, если указан параметр.|
|**NoClobber**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы ресурс не перезаписывался при указании параметра. Этот параметр обычно применяется к командлетам, которые создают новые объекты, что позволяет предотвратить перезапись существующих объектов с тем же именем.|
|**Явлении**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы пользователь получал уведомления о завершении действия, если указан параметр.|
|**нотифяддресс**<br>Тип данных: адрес электронной почты|Реализуйте этот параметр, чтобы пользователь мог указать адрес электронной почты, который будет использоваться для отправки уведомления, если указан параметр **Notify** .|
|**Перезаписать**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы командлет перезаписал все существующие данные при указании параметра.|
|**Предупреждение**<br>Тип данных: строка|Реализуйте этот параметр, чтобы пользователь мог указать запрос для командлета.|
|**Тихо**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы при указании параметра командлет подавляет Отзывы пользователей во время действий.|
|**Recurse**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы командлет рекурсивно выполнял свои действия с ресурсами, если указан параметр.|
|**Чинить**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы командлет предпринимал попытку исправить что-то из неработающего состояния, если указан параметр.|
|**репаирстринг**<br>Тип данных: строка|Реализуйте этот параметр, чтобы пользователь мог указать строку, используемую при указании параметра **Repair** .|
|**Повторите**<br>Тип данных: Int32|Реализуйте этот параметр, чтобы пользователь мог указать, сколько раз командлет будет пытаться выполнить действие.|
|**Метьте**<br>Тип данных: массив ключевых слов|Реализуйте этот параметр, чтобы пользователь мог указать массив типов элементов.|
|**Вышестоящий**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы пользователь мог передавать несколько выходных объектов через конвейер, если указан параметр.|
|**Ограничил**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы все ошибки обрабатывались как завершающие ошибки, если указан параметр.|
|**темплокатион**<br>Тип данных: строка|Реализуйте этот параметр, чтобы пользователь мог указать расположение временных данных, используемых при выполнении командлета.|
|**Счетчик**<br>Тип данных: Int32|Реализуйте этот параметр, чтобы пользователь мог указать интервал времени ожидания (в миллисекундах).|
|**TRUNCATE**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы командлет обрезает свои действия при указании параметра. Если параметр не указан, командлет выполняет еще одно действие.|
|**Проверка**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы командлет протестировать, чтобы определить, произошло ли действие при указании параметра.|
|**Ожидания**<br>Тип данных: переключатель|Реализуйте этот параметр, чтобы командлет предложит ввод пользователя, прежде чем продолжить, если указан параметр.
|**Время ожидания**<br>Тип данных: Int32|Реализуйте этот параметр, чтобы пользователь мог указать длительность (в секундах), в течение которого командлет будет ожидать ввода данных пользователем при указании параметра **Wait** .|

## <a name="see-also"></a>См. также:

[Параметры командлета](./cmdlet-parameters.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)