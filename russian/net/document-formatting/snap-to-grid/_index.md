---
title: Привязки к сетке
linktitle: Привязки к сетке
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по объяснению исходного кода C# функции Snap to Grid с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-formatting/snap-to-grid/
---

В этом руководстве мы расскажем вам, как использовать функцию «Привязать к сетке» с Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и применить изменения.

## Шаг 1: Создание и настройка документа

Для начала создайте новый документ и связанный с ним объект DocumentBuilder. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2: Выравнивание сетки

Теперь мы применим выравнивание по сетке к конкретному абзацу и используемому в абзаце шрифту. Вот как:

```csharp
// Включить выравнивание по сетке для абзаца
Paragraph by = doc.FirstSection.Body.FirstParagraph;
par.ParagraphFormat.SnapToGrid = true;

// Напишите текст в абзаце
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod" +
                 "tempor incident ut labore et dolore magna aliqua.");

// Включить выравнивание по сетке для шрифта, используемого в абзаце
par.Runs[0].Font.SnapToGrid = true;
```

## Шаг 3: Сохранение документа

 После вставки поля формы ввода текста сохраните документ в нужное место с помощью кнопки`Save` метод. Обязательно укажите правильный путь к файлу:

```csharp
doc.Save(dataDir + "Paragraph.SnapToGrid.docx");
```

### Пример исходного кода для Snap To Grid с использованием Aspose.Words для .NET

Вот полный исходный код функции Snap to Grid с Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Оптимизируйте макет при вводе азиатских символов.
	Paragraph par = doc.FirstSection.Body.FirstParagraph;
	par.ParagraphFormat.SnapToGrid = true;

	builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod " +
					"tempor incididunt ut labore et dolore magna aliqua.");
	
	par.Runs[0].Font.SnapToGrid = true;

	doc.Save(dataDir + "Paragraph.SnapToGrid.docx");

```

С помощью этого кода вы сможете выровнять текст по сетке и оптимизировать внешний вид документа с помощью Aspose.Words для .NET.

