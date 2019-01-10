---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Специальные возможности в интегрированной среде сценариев Windows PowerShell
ms.assetid: a078f9d1-dd6b-4323-b16d-0622cd993aa8
ms.openlocfilehash: 78a001dbe43a0b005d10a817e05e4cc7a72f5bd0
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402528"
---
# <a name="accessibility-in-windows-powershell-ise"></a>Специальные возможности в интегрированной среде сценариев Windows PowerShell

В этом разделе описываются специальные возможности интегрированной среды сценариев Windows PowerShell (ISE), которые могут помочь вам в работе.

* [Изменение размера и расположения областей консоли и сценариев](#how-to-change-the-size-and-location-of-the-console-and-script-panes)
* [Сочетания клавиш для редактирования текста](#keyboard-shortcuts-for-editing-text)
* [Сочетания клавиш для выполнения сценариев](#keyboard-shortcuts-for-running-scripts)
* [Сочетания клавиш для настройки представления](#keyboard-shortcuts-for-customizing-the-view)
* [Сочетания клавиш для отладки сценариев](#keyboard-shortcuts-for-debugging-scripts)
* [Сочетания клавиш для вкладок Windows PowerShell](#keyboard-shortcuts-for-windows-powershell-tabs)
* [Сочетания клавиш для запуска и выхода](#keyboard-shortcuts-for-starting-and-exiting)

Корпорация Майкрософт стремится стремится сделать использование своих продуктов и услуг простым для всех пользователей. В следующих разделах представлена информация о компонентах, продуктах и службах, повышающих доступность интегрированной среды сценариев Windows PowerShell для пользователей с ограниченными возможностями.

Интегрированная среда сценариев Windows PowerShell поддерживает режим высокой контрастности. Для пользователей с ослабленным зрением сведения о точках останова доступны через командлеты для управления точками останова, например [Get-PSBreakpoint](https://technet.microsoft.com/library/0bf48936-00ab-411c-b5e0-9b10a812a3c6) и [Set-PSBreakpoint](https://technet.microsoft.com/library/6afd5d2c-a285-4796-8607-3cbf49471420). Дополнительные сведения см. в разделе "Управление точками останова" в статье [Отладка сценариев в интегрированной среде сценариев Windows PowerShell](How-to-Debug-Scripts-in-Windows-PowerShell-ISE.md). Помимо специальных возможностей и служебных программ в составе Microsoft Windows, следующие функции обеспечивают легкий доступ к интегрированной среде сценариев Windows PowerShell для пользователей с физическими ограничениями:

- Сочетания клавиш

- Таблица цветовой подсветки синтаксиса и возможность изменять некоторые другие параметры цветов с помощью объекта сценария [$psISE.Options](https://technet.microsoft.com/library/75e2a76f-f3d1-490b-ad5d-e3829946aabb).

- Изменение размера текста

## <a name="how-to-change-the-size-and-location-of-the-console-and-script-panes"></a>Изменение размера и расположения областей консоли и сценариев

Следующие шаги можно использовать для изменения размера и расположения областей консоли и сценариев. При повторном открытии интегрированной среды сценариев Windows PowerShell изменения в размере и расположении сохранятся.

### <a name="to-resize-the-script-pane-and-console-pane"></a>Изменение размера областей консоли и сценариев

1. Наведите указатель мыши на линию, разделяющую области консоли и сценариев.

2. Когда указатель примет вид двусторонней стрелки, перетащите границу, чтобы изменить размер области.

### <a name="to-move-the-script-pane-and-console-pane"></a>Перемещение областей консоли и сценариев

Выполните одно из следующих действий.

- Чтобы поместить область сценариев над областью консоли, нажмите клавиши **CTRL+1**, щелкните значок **Показать область сценариев сверху** на панели инструментов или в меню **Вид** выберите пункт **Показать область сценариев сверху**.

- Чтобы поместить область сценариев справа от области консоли, нажмите клавиши **CTRL+2**, щелкните значок **Показать область сценариев справа** в меню **Вид** или выберите **Показать область сценариев справа**.

- Чтобы развернуть область сценариев, нажмите клавиши **CTRL+3**, щелкните значок **Развернуть область сценариев** в меню **Вид** или выберите **Развернуть область сценариев**.

- Чтобы развернуть область консоли и скрыть область сценариев, с правого края строки вкладок щелкните значок **Скрыть область сценариев** или отмените выбор параметра **Показать область сценариев** в меню **Вид**.

- Чтобы показать область сценариев при развернутой области консоли, с правого края строки вкладок щелкните значок **Показать область сценариев** или отмените выбор параметра **Показать область сценариев** в меню **Вид**.

## <a name="keyboard-shortcuts-for-editing-text"></a>Сочетания клавиш для редактирования текста

При редактировании текста можно использовать приведенные ниже сочетания клавиш.

|Действие|Сочетания клавиш|Область использования|
|----------|----------------------|----------|
|**Копировать**|CTRL+C|Область сценариев, область консоли|
|**Вырезать**|CTRL+X|Область сценариев, область консоли|
|**Поиск в сценарии**|CTRL+F|Область сценариев|
|**Поиск следующего элемента в сценарии**|F3|Область сценариев|
|**Поиск предыдущего элемента в сценарии**|SHIFT+F3|Область сценариев|
|**Вставить**|CTRL+V|Область сценариев, область консоли|
|**Повторить**|CTRL+Y|Область сценариев, область консоли|
|**Заменить в сценарии**|CTRL+H|Область сценариев|
|**Сохранить**|CTRL+S|Область сценариев|
|**Выбрать все**|CTRL+A|Область сценариев, область консоли|
|**Отменить**|CTRL+Z|Область сценариев, область консоли|

## <a name="keyboard-shortcuts-for-running-scripts"></a>Сочетания клавиш для выполнения сценариев

При запуске сценариев в области сценариев можно использовать приведенные ниже сочетания клавиш.

|Действие|Сочетание клавиш|
|----------|---------------------|
|**Создать**|CTRL+N|
|**Открыть**|CTRL+O|
|**Запустить**|F5|
|**Запуск выбранного**|F8|
|**Остановить выполнение**|CTRL+BREAK. CTRL+C можно использовать при однозначном контексте (при отсутствии выбранного текста).|
|**Переход** (к следующему сценарию)|CTRL + TAB **Примечание:** Переход к следующему сценарию работает только в том случае, если у вас есть всего одна вкладка PowerShell откройте, или у вас есть несколько вкладок PowerShell, когда фокус находится на области сценариев.|
|**Переход** (к предыдущему сценарию)|CTRL + SHIFT + TAB **Примечание:** Переход к предыдущему сценарию работает при наличии только вкладок PowerShell, или в том случае, если у вас есть несколько вкладок PowerShell и фокус находится на области сценариев.|

## <a name="keyboard-shortcuts-for-customizing-the-view"></a>Сочетания клавиш для настройки представления

Для настройки представления в интегрированной среде сценариев Windows PowerShell можно использовать приведенные ниже сочетания клавиш. Они доступны во всех областях приложения.

|Действие|Сочетание клавиш|
|----------|---------------------|
|**Перейти в область консоли**|CTRL+D|
|**Перейти в область сценариев**|CTRL+I|
|**Показать область сценариев**|CTRL+R|
|**Скрыть область сценариев**|CTRL+R|
||
|**Переместить область сценариев вверх**|CTRL+1|
|**Переместить область сценариев вправо**|CTRL+2|
|**Развернуть область сценариев**|CTRL+3|
|**Увеличить**|CTRL+ЗНАК ПЛЮС|
|**Уменьшить**|CTRL+ЗНАК МИНУС|

## <a name="keyboard-shortcuts-for-debugging-scripts"></a>Сочетания клавиш для отладки сценариев

При отладке сценариев можно использовать приведенные ниже сочетания клавиш.

|Действие|Сочетание клавиш|Область использования|
|----------|---------------------|----------|
|**Запустить или продолжить**|F5|Область сценариев при отладке сценария|
|**Шаг с заходом**|F11|Область сценариев при отладке сценария|
|**Шаг с обходом**|F10|Область сценариев при отладке сценария|
|**Шаг с выходом**|SHIFT+F11|Область сценариев при отладке сценария|
|**Отображение стека вызовов**|CTRL+SHIFT+D|Область сценариев при отладке сценария|
|**Список точек останова**|CTRL+SHIFT+L|Область сценариев при отладке сценария|
|**Переключить точку останова**|F9|Область сценариев при отладке сценария|
|**Удалить все точки останова**|CTRL+SHIFT+F9|Область сценариев при отладке сценария|
|**Остановить отладчик**|SHIFT+F5|Область сценариев при отладке сценария|

> [!NOTE]
>
> При отладке сценариев в интегрированной среде сценариев Windows PowerShell также можно использовать сочетания клавиш, предназначенные для консоли Windows PowerShell. Для этого необходимо ввести ярлык в области консоли и нажать клавишу ВВОД.

|Действие|Сочетание клавиш|Область использования|
|----------|---------------------|----------|
|**Продолжить**|C|Область консоли при отладке сценария|
|**Шаг с заходом**|S|Область консоли при отладке сценария|
|**Шаг с обходом**|V|Область консоли при отладке сценария|
|**Шаг с выходом**|O|Область консоли при отладке сценария|
|**Повтор последней команды** (для шага с заходом или шага с обходом)|ВВОД|Область консоли при отладке сценария|
|**Отображение стека вызовов**|K|Область консоли при отладке сценария|
|**Остановить отладку**|Q|Область консоли при отладке сценария|
|**Вывести сценарий**|L|Область консоли при отладке сценария|
|**Отобразить команды отладки для консоли**|H или ?|Область консоли при отладке сценария|

## <a name="keyboard-shortcuts-for-windows-powershell-tabs"></a>Сочетания клавиш для вкладок сценариев Windows PowerShell

При работе с вкладками Windows PowerShell можно использовать приведенные ниже сочетания клавиш.

|Действие|Сочетание клавиш|
|----------|---------------------|
|**Закрыть вкладку PowerShell**|CTRL+W|
|**Создать вкладку PowerShell**|CTRL+T|
|**Предыдущая вкладка PowerShell**|CTRL+SHIFT+TAB. Это сочетание клавиш работает только в том случае, если на вкладках PowerShell нет открытых файлов.|
|**Следующая вкладка Windows PowerShell**|CTRL+TAB. Это сочетание клавиш работает только в том случае, если на вкладках PowerShell нет открытых файлов.|

## <a name="keyboard-shortcuts-for-starting-and-exiting"></a>Сочетания клавиш для запуска и выхода

Для запуска консоли PowerShell (PowerShell.exe) или выхода из интегрированной среды сценариев Windows PowerShell можно использовать приведенные ниже сочетания клавиш.

|Действие|Сочетание клавиш|
|----------|---------------------|
|**Выйти**|ALT + F4|
|**Запуск PowerShell.exe** (консоль Windows PowerShell)|CTRL+SHIFT+P|

## <a name="see-also"></a>См. также

[Введение в интегрированную среду сценариев Windows PowerShell](Introducing-the-Windows-PowerShell-ISE.md)