---
title: Установить позицию сноски и конечной сноски
linktitle: Установить позицию сноски и конечной сноски
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как установить положение сносок и концевых сносок в документах Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

В этом пошаговом руководстве мы расскажем вам, как использовать Aspose.Words для .NET для установки положения сносок и концевых сносок в документе Word. Мы объясним предоставленный исходный код C# и покажем вам, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Инициализация объекта документа

 Сначала инициализируйте`Document` объект, указав путь к исходному документу:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Шаг 2: Установка положения сноски и концевой сноски

 Далее войдите в`FootnoteOptions` и`EndnoteOptions`свойства документа, чтобы установить положение сносок и концевых сносок. В этом примере мы устанавливаем положение сносок под текстом, а положение концевых сносок — в конце раздела:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Шаг 3: Сохранение документа

Наконец, сохраните измененный документ:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Вот и все! Вы успешно установили положение сносок и концевых сносок в документе Word, используя Aspose.Words для .NET.

### Пример исходного кода для установки позиции сноски и концевой сноски с использованием Aspose.Words для .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими конкретными требованиями.
