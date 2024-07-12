---
title: Управление содержимым поля со списком
linktitle: Управление содержимым поля со списком
second_title: API обработки документов Aspose.Words
description: Узнайте, как создать элемент управления содержимым поля со списком в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/combo-box-content-control/
---

В этом руководстве объясняется, как создать элемент управления содержимым поля со списком в документе Word с помощью Aspose.Words для .NET. Элементы управления содержимым поля со списком позволяют пользователям выбирать элемент из раскрывающегося списка.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"`с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте документ и StructuredDocumentTag.
 Создайте новый экземпляр`Document` класс и`StructuredDocumentTag` для представления элемента управления содержимым поля со списком. Указать`SdtType.ComboBox` как тип и`MarkupLevel.Block` в качестве уровня разметки для создания поля со списком на уровне блока.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Шаг 3. Добавьте элементы в поле со списком
 Добавьте элементы в поле со списком, используя`ListItems` собственность`StructuredDocumentTag` . Каждый элемент представлен`SdtListItem` объект, который принимает отображаемый текст и значение. В этом примере мы добавляем три элемента в поле со списком.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Шаг 4. Добавьте тег StructuredDocumentTag в документ.
 Добавьте элемент управления содержимым поля со списком к телу документа, используя команду`AppendChild` метод тела первого раздела документа.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Шаг 5: Сохраните документ
 Сохраните документ в указанную директорию, используя команду`Save` метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithSdt.ComboBoxContentControl.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Пример исходного кода для управления содержимым поля со списком с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

Вот и все! Вы успешно создали элемент управления содержимым поля со списком в документе Word с помощью Aspose.Words для .NET.