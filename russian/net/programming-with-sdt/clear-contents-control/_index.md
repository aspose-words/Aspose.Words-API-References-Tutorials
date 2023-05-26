---
title: Очистить контроль содержимого
linktitle: Очистить контроль содержимого
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как очистить содержимое элемента управления в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/clear-contents-control/
---

В этом руководстве показано, как очистить содержимое SDT в документе Word с помощью Aspose.Words для .NET. При очистке содержимого SDT удаляются все текстовые или дочерние узлы в элементе управления содержимым.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и работы с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ и получите тег StructuredDocumentTag.
 Загрузите документ Word с помощью`Document` конструктор, передавая путь к документу в качестве параметра. Затем извлеките желаемое`StructuredDocumentTag` из документа. В этом примере мы предполагаем, что SDT является первым дочерним узлом в документе.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Шаг 3. Очистите содержимое тега StructuredDocumentTag.
 Очистите содержимое SDT с помощью`Clear` метод. Это удаляет любой текст или дочерние узлы в элементе управления содержимым.

```csharp
sdt.Clear();
```

## Шаг 4: Сохраните документ
Сохраните измененный документ с помощью`Save` метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithSdt.ClearContentsControl.doc».

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Пример исходного кода для Clear Contents Control с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Вот и все! Вы успешно очистили содержимое StructuredDocumentTag в документе Word, используя Aspose.Words для .NET.