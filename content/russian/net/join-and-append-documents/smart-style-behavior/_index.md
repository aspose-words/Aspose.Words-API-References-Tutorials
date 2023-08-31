---
title: Умное поведение
linktitle: Умное поведение
second_title: API обработки документов Aspose.Words
description: Узнайте, как поддерживать интеллектуальное поведение при присоединении и добавлении документов Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/smart-style-behavior/
---

Это руководство проведет вас через процесс использования функции Smart Style Behavior в Aspose.Words для .NET. Эта функция позволяет вам присоединять и добавлять документы Word, сохраняя поведение умного стиля.

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

## Шаг 3. Вставьте разрыв страницы в целевой документ

 Чтобы добавленное содержимое отображалось на новой странице целевого документа, вы можете вставить разрыв страницы с помощью`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Шаг 4. Установите параметры поведения смарт-стиля

 Чтобы включить интеллектуальное поведение во время операции добавления, вам необходимо создать экземпляр`ImportFormatOptions` и установите`SmartStyleBehavior` собственность на`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## Шаг 5: добавьте исходный документ к целевому документу

 Теперь вы можете добавить исходный документ к целевому документу, используя`InsertDocument` метод`DocumentBuilder` сорт. Использовать`ImportFormatMode.UseDestinationStyles` параметр и передать`ImportFormatOptions` объект для поддержания поведения умного стиля.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Шаг 6: Сохраните окончательный документ

 Наконец, сохраните объединенный документ с включенной функцией Smart Style Behavior с помощью`Save` метод`Document` сорт.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### Пример исходного кода для Smart Style Behavior с использованием Aspose.Words для .NET

Вот полный исходный код функции Smart Style Behavior на C# с использованием Aspose.Words для .NET:
 
```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

Вот и все! Вы успешно внедрили функцию Smart Style Behavior с помощью Aspose.Words для .NET. Окончательный документ будет содержать объединенный контент с сохранением смарт-стиля.