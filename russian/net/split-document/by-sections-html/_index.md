---
title: По разделам HTML
linktitle: По разделам HTML
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как разбить документ Word на разделы Html с помощью Aspose.Words для .NET с полным примером кода.
type: docs
weight: 10
url: /ru/net/split-document/by-sections-html/
---

В этом примере мы покажем вам, как разделить документ Word на отдельные разделы в формате HTML, используя функцию By HTML Sections в Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и сгенерировать отдельные HTML-документы для каждого раздела.

## Шаг 1: Загрузка документа

Для начала укажите каталог для вашего документа и загрузите документ в объект Document. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Шаг 2: Разделение документа на разделы в формате HTML

Теперь мы установим параметры сохранения, чтобы разделить документ на разделы в формате HTML. Вот как это сделать:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### Пример исходного кода для HTML по разделам с использованием Aspose.Words для .NET

Вот полный исходный код функции By HTML Sections в Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Rendering.docx");

	
	HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };
	
	
	doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);

```

С помощью этого кода вы сможете разделить документ Word на отдельные разделы в формате HTML, используя Aspose.Words для .NET.

Теперь вы можете создавать отдельные HTML-документы для каждого раздела исходного документа.



