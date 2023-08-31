---
title: Объединение документов Word
linktitle: Объединить документы
second_title: API обработки документов Aspose.Words
description: Узнайте, как объединить несколько документов Word с помощью Aspose.Words для .NET. Этот мощный API упрощает процесс объединения документов, делая его эффективным и простым.
type: docs
weight: 10
url: /ru/net/split-document/merge-documents/
---

В этом уроке мы покажем вам, как объединить несколько документов Word с помощью функции «Объединить документы» в Aspose.Words для .NET. Выполните следующие действия, чтобы понять исходный код и получить объединенный документ, содержащий все исходные документы.

## Шаг 1. Найдите документы для объединения

Прежде чем объединять документы, нам необходимо найти исходные документы, которые нужно объединить. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Найдите документы для объединения.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Шаг 2. Объедините документы

Теперь мы объединим документы один за другим, чтобы создать окончательный объединенный документ. Вот как:

```csharp
// Откройте первую часть полученного документа.
Document sourceDoc = new Document(sourceDocumentPath);

// Создайте новый результирующий документ.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Объедините документы один за другим.
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

Вот полный исходный код функции слияния документов в Aspose.Words для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Найдите документы, используя для слияния.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Откройте первую часть полученного документа.
Document sourceDoc = new Document(sourceDocumentPath);

// Создайте новый результирующий документ.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Объедините части документа одну за другой.
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

## Заключение

Поздравляем! Вы узнали, как объединить несколько документов Word с помощью функции «Объединить документы» в Aspose.Words для .NET. Следуя предоставленному исходному коду, вы можете объединить отдельные документы в один объединенный документ, сохраняя при этом форматирование каждого исходного документа.

Объединение документов может оказаться полезным, если вы хотите объединить информацию из нескольких источников или создать единый документ из отдельных частей. Aspose.Words for .NET предоставляет мощный API, который упрощает процесс объединения документов, делая его эффективным и простым.

Не стесняйтесь изучать другие функции, предлагаемые Aspose.Words для .NET, чтобы расширить возможности обработки документов и оптимизировать рабочий процесс.

### Часто задаваемые вопросы

#### Как объединить документы с разным форматированием?

 При объединении документов Aspose.Words для .NET предоставляет возможность сохранить форматирование каждого исходного документа. С помощью`ImportFormatMode.KeepSourceFormatting` вариант, объединенный документ сохранит форматирование исходных документов. Если вы хотите применить единообразное форматирование ко всему объединенному документу, вы можете изменить форматирование с помощью API Aspose.Words после объединения документов.

#### Могу ли я объединить документы разных форматов?

Да, Aspose.Words for .NET поддерживает объединение документов в различных форматах, включая DOCX, DOC, RTF и другие. Вы можете загружать документы разных форматов в API Aspose.Words и объединять их в один документ независимо от их исходных форматов.

#### Могу ли я объединить документы со сложной структурой, например таблицы и изображения?

Абсолютно! Aspose.Words for .NET способен объединять документы со сложной структурой, включая таблицы, изображения, верхние и нижние колонтитулы и многое другое. API обрабатывает процесс слияния, сохраняя при этом целостность и структуру содержимого в каждом документе.

#### Можно ли объединить документы с разными ориентациями и размерами страниц?

Да, Aspose.Words для .NET обрабатывает документы с различной ориентацией или размером страницы в процессе объединения. Полученный объединенный документ будет соответствовать различным ориентациям страниц и размерам исходных документов.