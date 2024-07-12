---
title: Тип флажка Управление содержимым
linktitle: Тип флажка Управление содержимым
second_title: API обработки документов Aspose.Words
description: Узнайте, как создать элемент управления содержимым типа флажка в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/check-box-type-content-control/
---

В этом руководстве объясняется, как создать элемент управления содержимым типа флажка в документе Word с помощью Aspose.Words для .NET. Элементы управления содержимым флажка позволяют пользователям устанавливать или снимать флажок в документе.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"`с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте документ и DocumentBuilder
 Создайте новый экземпляр`Document` класс и`DocumentBuilder` для построения содержания документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Добавьте элемент управления содержимым типа флажка
 Создать`StructuredDocumentTag` с`SdtType.Checkbox` для представления элемента управления содержимым флажка. Указать`MarkupLevel.Inline` чтобы поместить его в текст.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Шаг 4. Сохраните документ
 Сохраните документ в указанную директорию, используя команду`Save`метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithSdt.CheckBoxTypeContentControl.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Пример исходного кода для управления содержимым типа флажка с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

Вот и все! Вы успешно создали элемент управления содержимым типа флажка в документе Word с помощью Aspose.Words для .NET.