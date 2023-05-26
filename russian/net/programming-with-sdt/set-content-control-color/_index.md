---
title: Установить цвет элемента управления содержимым
linktitle: Установить цвет элемента управления содержимым
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как установить цвет элемента управления содержимым в документе Word с помощью Aspose.Words для .NET, настроив его внешний вид.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/set-content-control-color/
---

В этом руководстве объясняется, как установить цвет элемента управления содержимым в документе Word с помощью Aspose.Words для .NET. Вы можете настроить внешний вид элементов управления содержимым, изменив их цвет.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и работы с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ и получите элемент управления содержимым
 Загрузите документ Word с помощью`Document` конструктор, передавая путь к документу в качестве параметра. Получите нужный элемент управления содержимым из документа. В этом примере мы предполагаем, что элемент управления содержимым является первым тегом структурированного документа в документе.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Шаг 3. Установите цвет элемента управления содержимым
 Установите цвет элемента управления содержимым, назначив`Color` значение для`Color` свойство тега структурированного документа. В этом примере мы установили красный цвет.

```csharp
sdt.Color = Color.Red;
```

## Шаг 4: Сохраните документ
 Сохраните измененный документ в указанную директорию с помощью`Save` метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithSdt.SetContentControlColor.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Пример исходного кода для установки цвета элемента управления содержимым с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

Вот и все! Вы успешно установили цвет элемента управления содержимым в документе Word с помощью Aspose.Words для .NET.