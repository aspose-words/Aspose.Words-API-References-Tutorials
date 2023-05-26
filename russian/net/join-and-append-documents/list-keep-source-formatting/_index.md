---
title: Список Сохранить исходное форматирование
linktitle: Список Сохранить исходное форматирование
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как сохранить форматирование списка при объединении и добавлении документов Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/list-keep-source-formatting/
---

Это руководство проведет вас через процесс использования функции форматирования списка и сохранения исходного кода в Aspose.Words для .NET. Эта функция позволяет объединять и добавлять документы Word, сохраняя при этом исходное форматирование списков.

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Шаг 3. Установите для исходного документа непрерывный поток

 Чтобы обеспечить непрерывную передачу содержимого из исходного документа при добавлении к целевому документу, необходимо установить`SectionStart` свойство первого раздела в исходном документе на`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Шаг 4: добавьте исходный документ к целевому документу

 Теперь вы можете добавить исходный документ к целевому документу, используя`AppendDocument` метод`Document` сорт.`ImportFormatMode.KeepSourceFormatting`Параметр обеспечивает сохранение исходного форматирования, включая форматирование списков, во время операции добавления.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 5: Сохраните окончательный документ

 Наконец, сохраните объединенный документ с включенной функцией List Keep Source Formatting с помощью кнопки`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Пример исходного кода для форматирования списка с сохранением исходного кода с использованием Aspose.Words для .NET 

Вот полный исходный код функции форматирования списка и сохранения исходного кода на C# с использованием Aspose.Words для .NET:

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Добавляйте содержимое документа, чтобы оно непрерывно перемещалось.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

Вот и все! Вы успешно реализовали функцию форматирования списка с сохранением исходного кода с помощью Aspose.Words для .NET. Окончательный документ будет содержать объединенный контент с сохраненным форматированием списка исходного документа.