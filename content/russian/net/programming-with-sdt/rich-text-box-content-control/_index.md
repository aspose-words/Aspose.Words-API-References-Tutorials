---
title: Элемент управления содержимым расширенного текстового поля
linktitle: Элемент управления содержимым расширенного текстового поля
second_title: API обработки документов Aspose.Words
description: Узнайте, как создать элемент управления содержимым поля форматированного текста в документе Word с помощью Aspose.Words для .NET, поддерживающего форматирование и стиль текста.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/rich-text-box-content-control/
---

В этом руководстве показано, как создать элемент управления содержимым поля форматированного текста в документе Word с помощью Aspose.Words для .NET. Элементы управления содержимым поля форматированного текста позволяют пользователям вводить и форматировать текст с использованием различных стилей и параметров форматирования.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и Word Processing с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте документ и StructuredDocumentTag
 Создайте новый экземпляр`Document` класс и`StructuredDocumentTag` для представления элемента управления содержимым поля форматированного текста. Указать`SdtType.RichText` как тип и`MarkupLevel.Block` в качестве уровня разметки для создания поля форматированного текста на уровне блока.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Шаг 3: Создайте и отформатируйте форматированный текстовый контент
Создайте абзац и запустите, чтобы представить содержимое форматированного текста. Установите параметры текста и форматирования, такие как цвет, шрифт и т. д.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Шаг 4. Добавьте форматированное текстовое содержимое в элемент управления содержимым.
Добавьте абзац с форматированным текстовым содержимым в`ChildNodes` коллекция элемента управления содержимым поля форматированного текста.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Шаг 5: добавьте элемент управления содержимым к документу
 Добавьте элемент управления содержимым поля форматированного текста к основной части документа с помощью`AppendChild` метод тела первого раздела документа.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Шаг 6: Сохраните документ
 Сохраните документ в указанную директорию с помощью`Save` метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithSdt.RichTextBoxContentControl.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Пример исходного кода для управления содержимым Rich Text Box с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
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