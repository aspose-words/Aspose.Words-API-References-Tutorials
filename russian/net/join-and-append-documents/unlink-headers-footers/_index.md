---
title: Отключить заголовки и нижние колонтитулы
linktitle: Отключить заголовки и нижние колонтитулы
second_title: API обработки документов Aspose.Words
description: Узнайте, как объединять и добавлять документы Word, одновременно удаляя верхние и нижние колонтитулы, используя Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/unlink-headers-footers/
---

Это руководство проведет вас через процесс использования функции Unlink Headers Footers в Aspose.Words для .NET. Эта функция позволяет вам присоединять и добавлять документы Word, отсоединяя верхние и нижние колонтитулы от исходного документа.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Aspose.Words для .NET установлен. Вы можете загрузить его с веб-сайта Aspose или установить через NuGet.
2. Visual Studio или любая другая среда разработки C#.

## Шаг 1: Инициализируйте каталоги документов

 Во-первых, вам нужно указать путь к папке с документами. Измените значение параметра`dataDir`переменная на путь, где находятся ваши документы.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите исходный и целевой документы

 Далее вам нужно загрузить исходный и конечный документы с помощью Aspose.Words.`Document` сорт. Обновите имена файлов в`Document` конструктор в соответствии с именами ваших документов.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3. Отсоедините верхние и нижние колонтитулы в исходном документе

 Чтобы отделить верхние и нижние колонтитулы исходного документа от продолжения верхних и нижних колонтитулов целевого документа, необходимо установить`LinkToPrevious`собственность`HeadersFooters` коллекция в первом разделе исходного документа для`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Шаг 4: добавьте исходный документ к целевому документу

 Теперь вы можете добавить исходный документ к целевому документу, используя`AppendDocument` метод`Document` сорт.`ImportFormatMode.KeepSourceFormatting` Параметр обеспечивает сохранение исходного форматирования во время операции добавления.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 5: Сохраните окончательный документ

Наконец, сохраните объединенный документ с включенной функцией Unlink Headers Footers с помощью`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Пример исходного кода для отмены связи заголовков и нижних колонтитулов с использованием Aspose.Words для .NET

Вот полный исходный код функции «Отключить заголовки и нижние колонтитулы» на C# с использованием Aspose.Words для .NET:

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Отсоедините верхние и нижние колонтитулы в исходном документе, чтобы остановить это.
	// от продолжения верхних и нижних колонтитулов целевого документа.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Вот и все! Вы успешно внедрили функцию «Отключить заголовки и нижние колонтитулы» с помощью Aspose.Words для .NET. Конечный документ будет содержать объединенное содержимое с верхними и нижними колонтитулами из исходного документа, не связанного с целевым документом.