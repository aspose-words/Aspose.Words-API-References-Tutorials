---
title: Показать скрыть содержимое закладок в документе Word
linktitle: Показать скрыть содержимое закладок в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как отображать и скрывать содержимое закладок в документах Word с помощью Aspose.Words for .NET, с помощью этого подробного пошагового руководства.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/show-hide-bookmarked-content/
---
## Введение

Готовы погрузиться в мир манипулирования документами с помощью Aspose.Words для .NET? Являетесь ли вы разработчиком, желающим автоматизировать задачи с документами, или просто человеком, интересующимся программной обработкой файлов Word, вы находитесь в правильном месте. Сегодня мы рассмотрим, как отображать и скрывать содержимое закладок в документе Word с помощью Aspose.Words для .NET. Это пошаговое руководство сделает вас профессионалом в управлении видимостью контента с помощью закладок. Давайте начнем!

## Предварительные условия

Прежде чем мы перейдем к подробностям, вам понадобится несколько вещей:

1. Visual Studio: любая версия, совместимая с .NET.
2.  Aspose.Words для .NET: загрузите его[здесь](https://releases.aspose.com/words/net/).
3. Базовое понимание C#: если вы можете написать простую программу «Hello World», все готово.
4. Документ Word с закладками. В этом уроке мы будем использовать образец документа с закладками.

## Импортировать пространства имен

Прежде всего, давайте импортируем необходимые пространства имен. Это гарантирует, что у нас есть все инструменты, необходимые для нашей задачи.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

Имея эти пространства имен, мы готовы начать наше путешествие.

## Шаг 1: Настройка вашего проекта

Хорошо, давайте начнем с настройки нашего проекта в Visual Studio.

### Создать новый проект

Откройте Visual Studio и создайте новый проект консольного приложения (.NET Core). Назовите его как-нибудь запоминающимся, например «BookmarkVisibilityManager».

### Добавить Aspose.Words для .NET

Вам нужно будет добавить Aspose.Words для .NET в свой проект. Вы можете сделать это через диспетчер пакетов NuGet.

1. Откройте Инструменты > Диспетчер пакетов NuGet > Управление пакетами NuGet для решения.
2. Найдите «Aspose.Words».
3. Установите пакет.

Большой! Теперь, когда наш проект настроен, давайте перейдем к загрузке нашего документа.

## Шаг 2. Загрузка документа

Нам нужно загрузить документ Word, содержащий закладки. В этом уроке мы будем использовать образец документа с именем «Bookmarks.docx».

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 Этот фрагмент кода устанавливает путь к каталогу вашего документа и загружает документ в папку.`doc` объект.

## Шаг 3. Показать/скрыть контент, добавленный в закладки

Теперь самое интересное — отображение или скрытие контента на основе закладок. Мы создадим метод под названием`ShowHideBookmarkedContent` справиться с этим.

Вот метод, который будет переключать видимость содержимого закладок:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    Node currentNode = bm.BookmarkStart;
    while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
    {
        if (currentNode.NodeType == NodeType.Run)
        {
            Run run = currentNode as Run;
            run.Font.Hidden = isHidden;
        }
        currentNode = currentNode.NextSibling;
    }
}
```

### Разбивка метода

-  Получение закладки:`Bookmark bm = doc.Range.Bookmarks[bookmarkName];` извлекает закладку.
- Обход узла: мы пересекаем узлы внутри закладки.
-  Переключатель видимости: если узел является`Run` (непрерывный фрагмент текста), мы устанавливаем его`Hidden` свойство.

## Шаг 4: Применение метода

Имея наш метод, давайте применим его для отображения или скрытия контента на основе закладки.

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true);
```

Эта строка кода скроет содержимое закладки с именем «MyBookmark1».

## Шаг 5: Сохранение документа

Наконец, давайте сохраним наш измененный документ.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

Это сохранит документ с внесенными нами изменениями.

## Заключение

И вот оно! Вы только что узнали, как отображать и скрывать содержимое закладок в документе Word с помощью Aspose.Words для .NET. Этот мощный инструмент упрощает работу с документами независимо от того, автоматизируете ли вы отчеты, создаете шаблоны или просто работаете с файлами Word. Приятного кодирования!

## Часто задаваемые вопросы

### Могу ли я переключать несколько закладок одновременно?
 Да, вы можете позвонить в`ShowHideBookmarkedContent` метод для каждой закладки, которую вы хотите переключить.

### Влияет ли сокрытие содержимого на структуру документа?
Нет, скрытие контента влияет только на его видимость. Содержимое остается в документе.

### Могу ли я использовать этот метод для других типов контента?
Этот метод специально переключает прогоны текста. Для других типов контента вам потребуется изменить логику обхода узла.

### Является ли Aspose.Words для .NET бесплатным?
 Aspose.Words предлагает бесплатную пробную версию[здесь](https://releases.aspose.com/) , но для производственного использования требуется полная лицензия. Вы можете купить его[здесь](https://purchase.aspose.com/buy).

### Как я могу получить поддержку, если у меня возникнут проблемы?
 Вы можете получить поддержку от сообщества Aspose[здесь](https://forum.aspose.com/c/words/8).