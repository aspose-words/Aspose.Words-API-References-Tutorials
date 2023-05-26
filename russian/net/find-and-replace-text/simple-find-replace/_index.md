---
title: Простой поиск замены
linktitle: Простой поиск замены
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как выполнить простой поиск и замену в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/find-and-replace-text/simple-find-replace/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию простого поиска и замены в библиотеке Aspose.Words для .NET. Эта функция позволяет выполнять простую замену текста путем поиска определенной строки символов и замены ее другой строкой символов в документе Word.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1: Создание нового документа

 Прежде чем мы начнем использовать простой поиск и замену, нам нужно создать новый документ, используя Aspose.Words для .NET. Это можно сделать, создав экземпляр`Document` объект:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Шаг 2. Вставьте текст в документ

 Когда у нас есть документ, мы можем вставить текст, используя`DocumentBuilder` объект. В нашем примере мы используем`Writeln` способ вставить фразу "Привет_CustomerName_,":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## Шаг 3: Простая замена текста

 Мы используем`Range.Replace` метод для выполнения простой замены текста. В нашем примере мы заменяем все вхождения строки "_ClientName_ " с "Джеймсом Бондом" с помощью`FindReplaceOptions` вариант с`FindReplaceDirection.Forward` направление поиска:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Шаг 4: Сохранение отредактированного документа

 Наконец, мы сохраняем измененный документ в указанный каталог, используя`Save` метод:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Пример исходного кода для простого поиска и замены с использованием Aspose.Words для .NET

Вот полный пример исходного кода, демонстрирующий использование простого поиска и замены в Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// Сохраните измененный документ
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию простого поиска и замены Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы создать документ, вставить текст, выполнить простую замену текста и сохранить отредактированный документ.
