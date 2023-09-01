---
title: Добавить документ
linktitle: Добавить документ
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить содержимое одного документа в другой с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/append-document/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для добавления содержимого одного документа в другой. Предоставленный исходный код демонстрирует, как открывать исходный и целевой документы, импортировать и добавлять разделы из исходного документа в целевой документ.

## Шаг 1. Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

-  Установлена библиотека Aspose.Words для .NET. Вы можете скачать его с[Aspose.Releases]https://releases.aspose.com/words/net/ или используйте менеджер пакетов NuGet для его установки.
- Путь к каталогу документов, в котором расположены исходные и целевые документы.

## Шаг 2. Откройте исходный и целевой документы.

 Откройте исходный и целевой документы с помощью`Document` конструктор класса. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3. Добавьте разделы из исходного документа в целевой документ.

 Просмотрите все разделы исходного документа и импортируйте каждый раздел в целевой документ, используя команду`ImportNode` метод. Затем добавьте импортированный раздел в целевой документ.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Шаг 4. Сохраните целевой документ

 Наконец, сохраните измененный целевой документ, используя команду`Save` метод`Document` объект.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

На этом реализация добавления документа с помощью Aspose.Words для .NET завершена.

### Пример исходного кода для добавления документа с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Просмотрите все разделы исходного документа.
	//Узлы разделов являются непосредственными дочерними элементами узла Document, поэтому мы можем просто перечислить Document.
	foreach (Section srcSection in srcDoc)
	{
		// Поскольку мы копируем раздел из одного документа в другой,
		// необходимо импортировать узел Раздел в целевой документ.
		// Это корректирует любые ссылки на стили, списки и т. д., специфичные для документа.
		//
		// Импорт узла создает копию исходного узла, но копия
		// ss готов к вставке в целевой документ.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Теперь новый узел раздела можно добавить к целевому документу.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```