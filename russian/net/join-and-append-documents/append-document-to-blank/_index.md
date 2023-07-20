---
title: Добавить документ в пустой
linktitle: Добавить документ в пустой
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить документ к пустому целевому документу в Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/append-document-to-blank/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для добавления содержимого одного документа к пустому целевому документу. Предоставленный исходный код демонстрирует, как создать новый документ, удалить его содержимое, а затем добавить к нему исходный документ.

## Шаг 1: Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

- Установлена библиотека Aspose.Words for .NET. Вы можете скачать его с[Aspose.Releases]https://releases.aspose.com/words/net/ или используйте диспетчер пакетов NuGet для его установки.
- Путь к каталогу документов, в котором находятся исходный и конечный документы.

## Шаг 2. Создайте новый целевой документ

 Создать новый`Document` объект для целевого документа.

```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Шаг 3. Удалите существующее содержимое из целевого документа.

 Чтобы обеспечить чистоту целевого документа, удалите все существующее содержимое из документа с помощью`RemoveAllChildren` метод.

```csharp
dstDoc.RemoveAllChildren();
```

## Шаг 4. Добавьте исходный документ к целевому документу.

 Добавьте содержимое исходного документа к целевому документу, используя`AppendDocument` метод с`ImportFormatMode.KeepSourceFormatting` вариант.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 5: Сохраните целевой документ

 Наконец, сохраните измененный целевой документ, используя`Save` метод`Document` объект.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

На этом реализация добавления документа к пустому целевому документу с использованием Aspose.Words for .NET завершена.

### Пример исходного кода для добавления документа к пустому с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	//Целевой документ не является пустым, что часто приводит к появлению пустой страницы перед добавленным документом.
	// Это связано с тем, что базовый документ имеет пустой раздел, а новый документ начинается на следующей странице.
	// Удалите все содержимое из целевого документа перед добавлением.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```