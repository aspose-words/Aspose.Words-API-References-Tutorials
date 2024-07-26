---
title: Управление содержимым поля форматированного текста
linktitle: Управление содержимым поля форматированного текста
second_title: API обработки документов Aspose.Words
description: Узнайте, как создать элемент управления содержимым поля форматированного текста в документе Word с помощью Aspose.Words для .NET, позволяющего форматировать и стилизовать текст.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/rich-text-box-content-control/
---

В этом руководстве показано, как создать элемент управления содержимым поля форматированного текста в документе Word с помощью Aspose.Words для .NET. Элементы управления содержимым форматированного текстового поля позволяют пользователям вводить и форматировать текст с использованием различных стилей и параметров форматирования.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте документ и StructuredDocumentTag.
 Создайте новый экземпляр`Document` класс и`StructuredDocumentTag` для представления элемента управления содержимым поля форматированного текста. Указать`SdtType.RichText` как тип и`MarkupLevel.Block` в качестве уровня разметки для создания поля форматированного текста на уровне блока.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Шаг 3. Создайте и отформатируйте форматированный текстовый контент
Создайте абзац и запустите его, чтобы представить содержимое форматированного текста. Установите параметры текста и форматирования, такие как цвет, шрифт и т. д.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Шаг 4. Добавьте форматированный текст в элемент управления содержимым
 Добавьте абзац с форматированным текстовым содержимым в`ChildNodes` коллекция элементов управления содержимым поля форматированного текста.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Шаг 5. Добавьте элемент управления содержимым в документ
 Добавьте элемент управления содержимым поля форматированного текста к телу документа с помощью`AppendChild` метод тела первого раздела документа.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Шаг 6: Сохраните документ
 Сохраните документ в указанную директорию, используя команду`Save`метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithSdt.RichTextBoxContentControl.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Пример исходного кода для управления содержимым поля форматированного текста с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

Вот и все! Вы успешно создали элемент управления содержимым поля форматированного текста в документе Word с помощью Aspose.Words для .NET.