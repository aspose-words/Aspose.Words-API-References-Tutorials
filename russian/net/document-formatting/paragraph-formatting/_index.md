---
title: Форматирование абзаца
linktitle: Форматирование абзаца
second_title: API обработки документов Aspose.Words
description: Узнайте, как применить пользовательское форматирование к абзацам с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-formatting/paragraph-formatting/
---

В этом руководстве мы расскажем вам, как использовать функцию форматирования абзаца с Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и применить изменения.

## Шаг 1: Создание и настройка документа

Для начала создайте новый документ и связанный с ним объект DocumentBuilder. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2: Форматирование абзаца

Теперь мы применим форматирование к абзацу, используя свойства, доступные в объекте ParagraphFormat объекта DocumentBuilder. Вот как:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.Alignment = ParagraphAlignment.Center;
paragraphFormat. LeftIndent = 50;
paragraphFormat. RightIndent = 50;
paragraphFormat. SpaceAfter = 25;
```

## Шаг 3: Сохранение документа

 После вставки поля формы ввода текста сохраните документ в нужное место с помощью кнопки`Save` метод. Обязательно укажите правильный путь к файлу:

```csharp
builder.Writeln(
	"I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
builder.Writeln(
	"I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");

doc.Save(dataDir + "DocumentFormatting.ParagraphFormatting.docx");
```

### Пример исходного кода для форматирования абзаца с использованием Aspose.Words для .NET

Вот полный исходный код функции форматирования абзаца с Aspose.Words для .NET:


```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.Alignment = ParagraphAlignment.Center;
	paragraphFormat.LeftIndent = 50;
	paragraphFormat.RightIndent = 50;
	paragraphFormat.SpaceAfter = 25;

	builder.Writeln(
		"I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
	builder.Writeln(
		"I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");

	doc.Save(dataDir + "DocumentFormatting.ParagraphFormatting.docx");
	
```

С помощью этого кода вы сможете применять различное форматирование к своим абзацам, используя Aspose.Words для .NET.

