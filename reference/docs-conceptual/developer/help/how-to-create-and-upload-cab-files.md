---
title: Как создавать и отправлять CAB-файлы
ms.date: 09/13/2016
ms.openlocfilehash: 247ed70ba206d70be01155653efbe887bf603f53
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893039"
---
# <a name="how-to-create-and-upload-cab-files"></a>Как создавать и отправлять CAB-файлы

В этом разделе описывается создание обновляемых CAB-файлов справки и их отправка в расположение, в котором можно найти обновляемые командлеты справки.

## <a name="how-to-create-and-upload-updatable-help-cab-files"></a>Создание и передача обновляемых CAB-файлов справки

Можно использовать функцию обновляемой справки для предоставления новых или обновленных файлов справки для модуля на нескольких языках и в разных культурах. Обновляемый пакет справки для модуля состоит из одного XML-файла HelpInfo и одного или нескольких файлов CAB ( `.CAB` ). Каждый CAB-файл содержит файлы справки для модуля в одном языке и региональных параметрах пользовательского интерфейса. Используйте следующую процедуру, чтобы создать CAB-файлы для обновляемой справки.

1. Упорядочите файлы справки для модуля по языку и региональным параметрам пользовательского интерфейса. Каждый обновляемый CAB-файл справки содержит файлы справки для одного модуля в одном языке и региональных параметрах пользовательского интерфейса. Для модуля можно предоставить несколько CAB-файлов справки для различных языков и региональных параметров пользовательского интерфейса.

1. Убедитесь, что файлы справки содержат только типы файлов, разрешенные для обновляемой справки, и проверьте их по схеме файла справки. Если `Update-Help` командлет встречает файл, который является недопустимым или не является разрешенным типом, он не устанавливает недопустимый файл и прекращает установку файлов из CAB-файла. Список разрешенных типов файлов см. в разделе [типы файлов, разрешенные в обновляемом CAB-файле справки](./file-types-permitted-in-an-updatable-help-cab-file.md).

1. Цифровая подпись файлов справки. Цифровые подписи не требуются, но рекомендуется использовать их.

1. Включите все файлы справки для модуля в языке и региональных параметрах пользовательского интерфейса, а не только новые или измененные файлы. Если CAB-файл неполон, пользователи, которые загружают файлы справки в первый раз или не загружают все обновления, не будут иметь все файлы справки по модулям.

1. Используйте служебную программу, которая создает CAB-файлы, например `MakeCab.exe` . PowerShell не включает командлеты, создающие CAB-файлы.

1. Присвойте имя CAB-файлам. Дополнительные сведения см. [в разделе именование обновляемого CAB-файла справки](./how-to-name-an-updatable-help-cab-file.md).

1. Передайте CAB-файлы для модуля в расположение, указанное элементом **хелпконтентури** в файле HelpInfo XML для модуля. Затем отправьте XML-файл HelpInfo в расположение, указанное ключом **HelpInfoUri** манифеста модуля. **Хелпконтентури** и **HelpInfoUri** могут указывать на одно и то же расположение.

> [!CAUTION]
> Значение ключа **HelpInfoUri** и элемент **хелпконтентури** должны начинаться с `http` или `https` . Значение должно указывать на расположение в Интернете и не должно включать имя файла.
