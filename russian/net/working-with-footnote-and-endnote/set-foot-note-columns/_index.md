---
title: Установить столбцы примечаний к ноте
linktitle: Установить столбцы примечаний к ноте
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как установить количество столбцов для сносок в документах Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-footnote-and-endnote/set-foot-note-columns/
---

В этом пошаговом руководстве мы расскажем, как использовать Aspose.Words для .NET, чтобы задать количество столбцов для сносок в документе Word. Мы объясним предоставленный исходный код C# и покажем вам, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Инициализация объекта документа

 Сначала инициализируйте`Document` объект, указав путь к исходному документу:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Шаг 2: Настройка столбцов сносок

 Далее войдите в`FootnoteOptions`свойство документа и установить`Columns` свойство, чтобы указать количество столбцов для сносок. В этом примере мы установили его в 3 столбца:

```csharp
doc.FootnoteOptions.Columns = 3;
```

## Шаг 3: Сохранение документа

Наконец, сохраните измененный документ:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

Вот и все! Вы успешно установили количество столбцов для сносок в документе Word, используя Aspose.Words для .NET.

### Пример исходного кода для установки столбцов сносок с использованием Aspose.Words для .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Document doc = new Document(dataDir + "Document.docx");

// Укажите количество столбцов, в которых форматируется область сносок.
doc.FootnoteOptions.Columns = 3;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими конкретными требованиями.