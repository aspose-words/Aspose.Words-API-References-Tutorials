---
title: Простое добавление документа
linktitle: Простое добавление документа
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как объединять и добавлять документы Word с сохраненным форматированием с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/simple-append-document/
---

Этот учебник проведет вас через процесс использования функции простого добавления документа в Aspose.Words для .NET. Эта функция позволяет присоединять и добавлять документы Word без дополнительных параметров.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Aspose.Words для .NET установлен. Вы можете загрузить его с веб-сайта Aspose или установить через NuGet.
2. Visual Studio или любая другая среда разработки C#.

## Шаг 1: Инициализируйте каталоги документов

 Во-первых, вам нужно указать путь к папке с документами. Измените значение параметра`dataDir` переменная на путь, где находятся ваши документы.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите исходный и целевой документы

 Далее вам нужно загрузить исходный и конечный документы с помощью Aspose.Words.`Document` сорт. Обновите имена файлов в`Document` конструктор в соответствии с именами ваших документов.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3: добавьте исходный документ к целевому документу

 Теперь вы можете добавить исходный документ к целевому документу, используя`AppendDocument` метод`Document` сорт.`ImportFormatMode.KeepSourceFormatting` Параметр обеспечивает сохранение исходного форматирования во время операции добавления.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 4: Сохраните окончательный документ

 Наконец, сохраните объединенный документ с помощью функции простого добавления документа, используя`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Пример исходного кода для простого добавления документа с использованием Aspose.Words для .NET

Вот полный исходный код функции «Простое добавление документа» на C# с использованием Aspose.Words для .NET:

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Добавьте исходный документ к целевому документу без дополнительных параметров.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

Вот и все! Вы успешно реализовали функцию простого добавления документа с помощью Aspose.Words для .NET. Конечный документ будет содержать объединенный контент с сохранением исходного форматирования.