---
title: Очистить контроль содержимого
linktitle: Очистить контроль содержимого
second_title: API обработки документов Aspose.Words
description: Узнайте, как очистить содержимое элемента управления в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/clear-contents-control/
---

В этом руководстве показано, как очистить содержимое SDT в документе Word с помощью Aspose.Words для .NET. При очистке содержимого SDT удаляются все текстовые или дочерние узлы внутри элемента управления содержимым.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ и получите тег StructuredDocumentTag.
 Загрузите документ Word, используя`Document` конструктор, передавая путь к документу в качестве параметра. Затем извлеките желаемый`StructuredDocumentTag`из документа. В этом примере мы предполагаем, что SDT является первым дочерним узлом в документе.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Шаг 3. Очистите содержимое StructuredDocumentTag.
 Очистите содержимое SDT с помощью`Clear` метод. При этом удаляются все текстовые или дочерние узлы внутри элемента управления содержимым.

```csharp
sdt.Clear();
```

## Шаг 4. Сохраните документ
 Сохраните измененный документ, используя`Save` метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithSdt.ClearContentsControl.doc».

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Пример исходного кода для Clear Content Control с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Вот и все! Вы успешно очистили содержимое StructuredDocumentTag в документе Word с помощью Aspose.Words для .NET.