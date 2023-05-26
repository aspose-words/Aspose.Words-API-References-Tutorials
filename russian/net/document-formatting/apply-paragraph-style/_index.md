---
title: Применить стиль абзаца
linktitle: Применить стиль абзаца
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как применить стиль абзаца с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-formatting/apply-paragraph-style/
---

В этом руководстве мы расскажем, как применить стиль абзаца с помощью Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и применить стиль абзаца.

## Шаг 1: Создание и настройка документа

Для начала создайте новый документ и связанный с ним объект DocumentBuilder. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Настройка стиля абзаца

Теперь мы настроим стиль абзаца, используя встроенный идентификатор стиля. Вот как:

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## Шаг 3. Добавьте контент

Мы собираемся добавить содержимое в абзац. Вот как:

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### Пример исходного кода для применения стиля абзаца с использованием Aspose.Words для .NET

Вот полный исходный код функции «Применить стиль абзаца» в Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

С помощью этого кода вы сможете применить стиль абзаца, используя Aspose.Words для .NET.

