---
title: Удалить нижние колонтитулы исходных заголовков
linktitle: Удалить нижние колонтитулы исходных заголовков
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как удалять верхние и нижние колонтитулы при присоединении и добавлении документов Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/remove-source-headers-footers/
---

Это руководство проведет вас через процесс использования функции «Удалить исходные заголовки и нижние колонтитулы» в Aspose.Words для .NET. Эта функция позволяет вам присоединять и добавлять документы Word, удаляя верхние и нижние колонтитулы из исходного документа.

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

## Шаг 3. Удалите верхние и нижние колонтитулы из разделов исходного документа

 Чтобы удалить верхние и нижние колонтитулы из каждого раздела в исходном документе, вы можете выполнить итерацию по разделам, используя`foreach` зациклить и вызвать`ClearHeadersFooters` метод.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Шаг 4. Отключите настройку «LinkToPrevious» для HeadersFooters.

Даже после очистки верхних и нижних колонтитулов исходного документа существует вероятность того, что параметр «LinkToPrevious» для`HeadersFooters` еще можно поставить. Чтобы избежать такого поведения, вам нужно явно установить его в`false` для первой секции`HeadersFooters` свойство.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Шаг 5: добавьте исходный документ к целевому документу

 Теперь вы можете добавить исходный документ к целевому документу, используя`AppendDocument` метод`Document` сорт.`ImportFormatMode.KeepSourceFormatting` Параметр обеспечивает сохранение исходного форматирования во время операции добавления.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 6: Сохраните окончательный документ

 Наконец, сохраните объединенный документ с включенной функцией удаления нижних колонтитулов источника с помощью`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Пример исходного кода для удаления нижних колонтитулов исходных заголовков с использованием Aspose.Words для .NET 

Вот полный исходный код функции «Удалить нижние колонтитулы исходных заголовков» на C# с использованием Aspose.Words для .NET:


```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Удалите верхние и нижние колонтитулы из каждого раздела исходного документа.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Даже после удаления верхних и нижних колонтитулов из исходного документа параметр «LinkToPrevious»
	// для HeadersFooters все еще можно установить. Это приведет к тому, что верхние и нижние колонтитулы будут продолжаться с места назначения.
	// документ. Это должно быть установлено в false, чтобы избежать такого поведения.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
Вот и все! Вы успешно реализовали функцию удаления нижних колонтитулов исходных заголовков с помощью Aspose.Words для .NET. Окончательный документ будет содержать объединенный контент с удаленными верхними и нижними колонтитулами из исходного документа.