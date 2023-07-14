---
title: Сравнить варианты
linktitle: Сравнить варианты
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по объяснению исходного кода C# функции сравнения параметров с Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/compare-documents/compare-options/
---

В этом руководстве мы объясним, как использовать функцию сравнения параметров с Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и применить изменения.

## Шаг 1. Сравните документы с пользовательскими параметрами

 Для начала загрузите два документа для сравнения. В этом примере мы будем использовать`Clone()` способ создания копии исходного документа. Вот как:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## Шаг 2. Настройка параметров сравнения

 Теперь мы настроим параметры сравнения, создав`CompareOptions` объект и установка различных свойств по мере необходимости. Вот как:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## Шаг 3. Сравните документы с пользовательскими параметрами

 Теперь мы будем использовать`Compare()` метод, передающий пользовательские параметры для сравнения двух документов. Этот метод пометит изменения в исходном документе. Вот как:

```csharp
// Сравните документы с пользовательскими параметрами
docA.Compare(docB, "user", DateTime.Now, options);

// Проверить, совпадают ли документы
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Пример исходного кода для параметров сравнения с использованием Aspose.Words для .NET

Вот полный исходный код функции сравнения параметров с Aspose.Words для .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

С помощью этого кода вы можете сравнить два документа, используя пользовательские параметры, чтобы игнорировать определенные элементы при сравнении с Aspose.Words для .NET.

