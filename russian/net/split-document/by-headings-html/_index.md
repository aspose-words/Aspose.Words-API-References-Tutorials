---
title: По заголовкам HTML
linktitle: По заголовкам HTML
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по объяснению исходного кода C# функции By Heading HTML в Aspose.Words для .NET
type: docs
weight: 10
url: /ru/net/split-document/by-headings-html/
---
В этом руководстве мы покажем вам, как разделить документ Word на более мелкие части с помощью функции «По заголовку HTML» в Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и сгенерировать отдельные HTML-документы на основе заголовка.

## Шаг 1: Загрузка документа

Для начала укажите каталог для вашего документа и загрузите документ в объект Document. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Шаг 2: Разделение документа по заголовку в формате HTML

Теперь мы установим параметры сохранения, чтобы разделить документ на более мелкие части на основе заголовка в формате HTML. Вот как:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Разделите документ на более мелкие части, в данном случае разделив его по заголовку.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Пример исходного кода для HTML по заголовкам с использованием Aspose.Words для .NET

Вот полный исходный код функции By HTML Heading в Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Rendering.docx");

	HtmlSaveOptions options = new HtmlSaveOptions
	{
		// Разделите документ на более мелкие части, в данном случае по заголовку.
		DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
	};
	

	doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
	

```

С помощью этого кода вы сможете разбить документ Word на более мелкие части с помощью Aspose.Words для .NET на основе заголовков. Затем вы можете создавать отдельные HTML-документы для каждой части.

