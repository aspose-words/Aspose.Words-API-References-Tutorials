---
title: Изменить интервал и отступ азиатского абзаца
linktitle: Изменить интервал и отступ азиатского абзаца
second_title: API обработки документов Aspose.Words
description: Узнайте, как изменить расстояние между абзацами и отступы для азиатских стран с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---

В этом руководстве мы расскажем, как изменить интервалы и отступы азиатского абзаца с помощью Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и применить изменения.

## Шаг 1: Загрузка документа

Для начала укажите каталог для ваших документов и загрузите документ, содержащий азиатскую типографику, в объект Document. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Шаг 2. Изменение интервала между абзацами и отступов

Теперь мы изменим интервалы и отступы первого абзаца азиатского документа. Вот как:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Обновить ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Обновить ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; // Обновить ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Обновить ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Обновить ParagraphFormat.SpaceAfter
```

## Шаг 3: Сохранение документа

 После вставки поля формы ввода текста сохраните документ в нужное место с помощью кнопки`Save` метод. Обязательно укажите правильный путь к файлу:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Пример исходного кода для изменения интервалов и отступов азиатских абзацев с использованием Aspose.Words для .NET

Вот полный исходный код функции редактирования интервалов и отступов азиатских абзацев с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent будет обновлен
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent будет обновлен
	format.CharacterUnitFirstLineIndent = 20;  //ParagraphFormat.FirstLineIndent будет обновлен
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore будет обновлен
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter будет обновлен

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

С помощью этого кода вы сможете изменить интервалы и отступы азиатского абзаца, используя Aspose.Words для .NET.

