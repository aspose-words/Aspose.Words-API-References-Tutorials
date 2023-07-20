---
title: Изменить азиатский интервал между абзацами и отступы в документе Word
linktitle: Изменить азиатский интервал между абзацами и отступы в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как изменить азиатский интервал между абзацами и отступы в документе Word с помощью Aspose.Words для .NET.
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
format.CharacterUnitFirstLineIndent = 20; //Обновить ParagraphFormat.FirstLineIndent
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
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent будет обновлен
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore будет обновлен
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter будет обновлен

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

С помощью этого кода вы сможете изменить интервалы и отступы азиатского абзаца, используя Aspose.Words для .NET.

## Заключение

 В этом руководстве мы узнали, как изменить интервалы и отступы азиатского абзаца с помощью Aspose.Words для .NET. Путем изменения соответствующих свойств`ParagraphFormat`мы можем управлять макетом и внешним видом азиатских абзацев в документе Word. Эта функция полезна для настройки форматирования текста с азиатскими символами и достижения желаемого визуального представления в документах со смешанным языковым содержимым.

### Часто задаваемые вопросы

#### В: Что делает функция «Изменить расстояние между азиатскими абзацами и отступы» в Aspose.Words для .NET?

О: Функция «Изменить интервалы и отступы азиатских абзацев» в Aspose.Words для .NET позволяет изменять свойства интервалов и отступов азиатского абзаца в документе Word. Вы можете настроить левый и правый отступы, отступ первой строки, отступ до и отступ после значений, чтобы управлять макетом и внешним видом абзаца.

#### В: Как изменить интервалы и отступы азиатского абзаца с помощью Aspose.Words for .NET?

 О: Чтобы изменить интервалы и отступы азиатского абзаца, вам нужно получить доступ к`ParagraphFormat`целевого абзаца и изменить его соответствующие свойства. В приведенном примере кода мы получаем доступ к первому абзацу документа и устанавливаем`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , и`LineUnitAfter` свойства для настройки интервалов и отступов.

#### В: Могу ли я применить эти изменения к другим абзацам документа?

 О: Да, вы можете применить эти изменения к другим абзацам в документе, обратившись к их соответствующим`ParagraphFormat` объекты. Пример кода предназначен для первого абзаца документа, но вы можете изменить другие абзацы, изменив индекс в`Paragraphs` коллекции или используя другие критерии, чтобы выбрать нужные абзацы.