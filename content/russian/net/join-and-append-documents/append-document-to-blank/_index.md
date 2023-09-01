---
title: Добавить документ в пустой список
linktitle: Добавить документ в пустой список
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить документ к пустому целевому документу в Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/append-document-to-blank/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для добавления содержимого одного документа в пустой целевой документ. Предоставленный исходный код демонстрирует, как создать новый документ, удалить его содержимое, а затем добавить к нему исходный документ.

## Шаг 1. Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

-  Установлена библиотека Aspose.Words для .NET. Вы можете скачать его с[Aspose.Releases]https://releases.aspose.com/words/net/ или используйте менеджер пакетов NuGet для его установки.
- Путь к каталогу документов, в котором расположены исходные и целевые документы.

## Шаг 2. Создайте новый целевой документ

 Создать новый`Document` объект для целевого документа.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Шаг 3. Удалите существующее содержимое из целевого документа.

 Чтобы обеспечить чистоту целевого документа, удалите из него все существующее содержимое с помощью команды`RemoveAllChildren` метод.

```csharp
dstDoc.RemoveAllChildren();
```

## Шаг 4. Добавьте исходный документ в целевой документ.

 Добавьте содержимое исходного документа в целевой документ, используя команду`AppendDocument` метод с`ImportFormatMode.KeepSourceFormatting` вариант.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 5. Сохраните целевой документ.

 Наконец, сохраните измененный целевой документ, используя команду`Save` метод`Document` объект.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

На этом реализация добавления документа к пустому целевому документу с помощью Aspose.Words для .NET завершена.

### Пример исходного кода для добавления документа в бланк с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// Целевой документ не пуст, поэтому перед добавленным документом часто появляется пустая страница.
	// Это связано с тем, что базовый документ имеет пустой раздел, а новый документ начинается на следующей странице.
	// Перед добавлением удалите все содержимое из целевого документа.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```