---
title: Сравнить на равных
linktitle: Сравнить на равных
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по объяснению исходного кода C# функции Compare for Equals с Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/compare-documents/compare-for-equal/
---

В этом руководстве мы расскажем, как использовать функцию «Сравнить на предмет равенства» с Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и применить изменения.

## Шаг 1: Сравнение документов

 Для начала загрузите два документа для сравнения. В этом примере мы будем использовать`Clone()` способ создания копии исходного документа. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document docA = new Document(dataDir + "Document.docx");
Document docB = docA.Clone();
```

## Шаг 2: Сравнение документов

 Теперь мы будем использовать`Compare()` Метод сравнения двух документов. Этот метод пометит изменения в исходном документе. Вот как:

```csharp
// Сравните документы
docA.Compare(docB, "user", DateTime.Now);

// Проверить, совпадают ли документы
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are identical": "Documents are not identical");
```

### Пример исходного кода для Compare For Equal с использованием Aspose.Words для .NET

Вот полный исходный код функции «Сравнить на равенство» с Aspose.Words для .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();
	
	// DocA теперь содержит изменения как ревизии.
	docA.Compare(docB, "user", DateTime.Now);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

С помощью этого кода вы сможете сравнить два документа и определить, являются ли они одинаковыми, используя Aspose.Words для .NET.

