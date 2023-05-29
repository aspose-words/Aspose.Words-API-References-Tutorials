---
title: Объединить документы
linktitle: Объединить документы
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по объяснению исходного кода C# функции слияния документов в Aspose.Words для .NET
type: docs
weight: 10
url: /ru/net/split-document/merge-documents/
---

В этом руководстве мы расскажем вам, как объединить несколько документов Word с помощью функции «Объединить документы» в Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и получить объединенный документ, содержащий все исходные документы.

## Шаг 1. Найдите документы для объединения

Перед объединением документов нам необходимо найти исходные документы, которые необходимо объединить. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Найдите документы для слияния.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Шаг 2. Объедините документы

Теперь мы объединим документы один за другим, чтобы создать окончательный объединенный документ. Вот как:

```csharp
// Откройте первую часть получившегося документа.
Document sourceDoc = new Document(sourceDocumentPath);

// Создайте новый результирующий документ.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Объединяйте документы один за другим.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### Пример исходного кода для объединения документов с использованием Aspose.Words для .NET

Вот полный исходный код функции слияния документов Aspose.Words для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Найдите документы, используя для слияния.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Откройте первую часть получившегося документа.
Document sourceDoc = new Document(sourceDocumentPath);

// Создайте новый результирующий документ.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Объединяйте части документа одну за другой.
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```
