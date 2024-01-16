---
title: Форматирование многоуровневого списка в документе Word
linktitle: Форматирование многоуровневого списка в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как создать многоуровневый список и применить собственное форматирование в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-formatting/multilevel-list-formatting/
---
В этом уроке мы покажем вам, как использовать функцию многоуровневого форматирования списка в документе Word с Aspose.Words для .NET. Выполните следующие действия, чтобы понять исходный код и применить изменения.

## Шаг 1. Создание и настройка документа

Для начала создайте новый документ и связанный с ним объект DocumentBuilder. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Форматирование многоуровневого списка

Теперь мы применим форматирование многоуровневого списка, используя методы, доступные в объекте DocumentBuilder. Вот как:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Шаг 3: Сохранение документа

 После вставки поля формы ввода текста сохраните документ в нужное место с помощью кнопки`Save` метод. Обязательно укажите правильный путь к файлу:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Пример исходного кода для форматирования многоуровневого списка с использованием Aspose.Words для .NET

Вот полный исходный код функции форматирования многоуровневого списка с помощью Aspose.Words для .NET:


```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

С помощью этого кода вы сможете создать многоуровневый список и применить правильное форматирование к каждому уровню, используя Aspose.Words для .NET.


## Заключение

В этом уроке мы рассмотрели процесс использования функции форматирования многоуровневого списка в документе Word с помощью Aspose.Words для .NET. Следуя описанным шагам, вы сможете создавать хорошо организованные списки с несколькими уровнями, улучшая структуру и читабельность ваших документов.

### Часто задаваемые вопросы

#### Вопрос: Что такое многоуровневый список в документе Word?

О: Многоуровневый список в документе Word представляет собой иерархический список, который позволяет организовывать элементы по различным уровням подэлементов. Это помогает представить информацию в структурированном виде, облегчая читателям понимание содержания.

#### Вопрос: Могу ли я настроить внешний вид многоуровневого списка?

О: Да, вы можете настроить внешний вид многоуровневого списка в документе Word. Применяя различные стили, такие как маркеры, цифры или буквы, а также регулируя отступы и интервалы, вы можете создать визуально привлекательный и организованный список.

#### Вопрос: Поддерживает ли Aspose.Words для .NET другие параметры форматирования списков?

О: Да, Aspose.Words для .NET предоставляет полный набор функций для форматирования списков. Он поддерживает различные типы списков, включая маркированные списки, нумерованные списки и многоуровневые списки. Вы можете управлять форматированием списков, добавлять или удалять элементы, а также настраивать их внешний вид.

#### Вопрос: Могу ли я использовать Aspose.Words для .NET для работы с другими элементами документа?

О: Да, Aspose.Words for .NET предлагает широкие возможности для работы с различными элементами документа, такими как абзацы, таблицы, изображения и многое другое. Он позволяет создавать, изменять и конвертировать документы Word программным способом, оптимизируя задачи обработки документов.