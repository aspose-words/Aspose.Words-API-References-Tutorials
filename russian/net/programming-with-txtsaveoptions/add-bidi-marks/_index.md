---
title: Добавить метки двунаправленного текста
linktitle: Добавить метки двунаправленного текста
second_title: Справочник по API Aspose.Words для .NET
description: Научитесь добавлять метки двунаправленного текста в документ Word с помощью Aspose.Words для .NET и создавать профессиональные многоязычные документы.
type: docs
weight: 10
url: /ru/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET — это мощная библиотека для создания, редактирования и управления документами Word в приложении C#. Среди функций, предлагаемых Aspose.Words, есть возможность добавлять в документ двунаправленные (двунаправленные) метки. В этом руководстве мы расскажем, как использовать исходный код C# Aspose.Words для .NET для добавления меток двунаправленного текста в документ.

## Понимание библиотеки Aspose.Words

Прежде чем погрузиться в код, важно понять библиотеку Aspose.Words для .NET. Aspose.Words — популярная библиотека, которая делает работу с документами Word простой и эффективной. Он предлагает широкий спектр функций для создания, редактирования и управления документами Word, включая добавление меток двунаправленного текста.

## Создание документа и добавление содержимого

Первый шаг — создать новый документ и добавить в него содержимое. Используйте класс Document для создания нового экземпляра документа. Затем используйте класс DocumentBuilder, чтобы добавить текст в документ. Вот пример:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

В этом примере мы создаем новый документ и используем DocumentBuilder для добавления текста. Мы добавили три строки текста: одну на английском, одну на иврите и одну на арабском, чтобы продемонстрировать добавление контента на разных языках.

## Добавлены метки биди

После добавления контента мы можем добавить в документ метки двунаправленного текста. Для этого мы используем класс TxtSaveOptions и устанавливаем для свойства AddBidiMarks значение true. Вот как:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

В этом примере мы создаем экземпляр TxtSaveOptions и устанавливаем для свойства AddBidiMarks значение true. Затем мы используем метод Save класса Document, чтобы сохранить документ с метками двунаправленного текста.

### Пример исходного кода для функции «Добавить двунаправленные метки» с Aspose.Words для .NET

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте документ и добавьте содержимое
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Добавить метки двунаправленного текста
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Заключение

В этом руководстве мы объяснили, как использовать Aspose.Words для .NET для добавления меток двунаправленного текста в документ Word с использованием предоставленного исходного кода C#. Следуя приведенным инструкциям, вы можете легко добавлять метки двунаправленного текста в документы Word в приложении C#. Aspose.Words предлагает невероятную гибкость и мощность для работы с форматированием текста и управлением языками, позволяя профессионально создавать многоязычные документы.