---
title: Группа разрывов строк азиатской типографии
linktitle: Группа разрывов строк азиатской типографии
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как использовать группу разрывов строк азиатской типографики с Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-formatting/asian-typography-line-break-group/
---

В этом уроке мы покажем вам, как использовать функцию разрыва строки азиатской типографики с Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и применить изменения форматирования.

## Шаг 1: Загрузка документа

Для начала укажите каталог для ваших документов и загрузите документ, содержащий азиатскую типографику, в объект Document. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Шаг 2: Настройка азиатской типографики

Теперь мы настроим параметры азиатской типографики для первого абзаца документа. Вот как:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Шаг 3: Сохранение документа

 После вставки поля формы ввода текста сохраните документ в нужное место с помощью кнопки`Save` метод. Обязательно укажите правильный путь к файлу:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Пример исходного кода для группы разрывов строк азиатской типографики с использованием Aspose.Words для .NET

Вот полный исходный код для функции разрыва строки азиатской типографики с Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
С помощью этого кода вы сможете применять группу разрывов строк азиатской типографики, используя Aspose.Words для .NET.

