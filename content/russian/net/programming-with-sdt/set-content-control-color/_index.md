---
title: Установить цвет элемента управления контентом
linktitle: Установить цвет элемента управления контентом
second_title: API обработки документов Aspose.Words
description: Узнайте, как установить цвет элемента управления содержимым в документе Word с помощью Aspose.Words для .NET, настроив его внешний вид.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/set-content-control-color/
---

В этом руководстве объясняется, как установить цвет элемента управления содержимым в документе Word с помощью Aspose.Words для .NET. Вы можете настроить внешний вид элементов управления содержимым, изменив их цвет.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ и получите элемент управления содержимым
 Загрузите документ Word, используя`Document` конструктор, передавая путь к документу в качестве параметра. Получите желаемый элемент управления содержимым из документа. В этом примере мы предполагаем, что элемент управления содержимым — это первый структурированный тег документа в документе.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Шаг 3. Установите цвет элемента управления контентом
 Установите цвет элемента управления содержимым, назначив`Color` ценность для`Color` свойство тега структурированного документа. В этом примере мы установили красный цвет.

```csharp
sdt.Color = Color.Red;
```

## Шаг 4. Сохраните документ
 Сохраните измененный документ в указанную директорию, используя команду`Save` метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithSdt.SetContentControlColor.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Пример исходного кода для установки цвета управления содержимым с помощью Aspose.Words для .NET 

```csharp
	//Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

Вот и все! Вы успешно установили цвет элемента управления содержимым в документе Word с помощью Aspose.Words для .NET.