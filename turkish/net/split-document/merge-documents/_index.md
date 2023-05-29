---
title: Belgeleri Birleştir
linktitle: Belgeleri Birleştir
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'in Belgeleri Birleştir özelliğinin C# kaynak kodunu açıklayan adım adım kılavuz
type: docs
weight: 10
url: /tr/net/split-document/merge-documents/
---

Bu öğreticide, Aspose.Words for .NET'in Belgeleri Birleştir özelliğini kullanarak birden çok Word belgesini nasıl birleştireceğinizi size göstereceğiz. Kaynak kodunu anlamak ve tüm kaynak belgeleri içeren birleştirilmiş bir belge elde etmek için aşağıdaki adımları izleyin.

## 1. Adım: Birleştirilecek belgeleri arayın

Belgeleri birleştirmeden önce, birleştirilecek kaynak belgeleri bulmamız gerekiyor. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Birleştirilecek belgeleri arayın.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## 2. Adım: Belgeleri birleştirin

Şimdi son birleştirilmiş belgeyi oluşturmak için belgeleri tek tek birleştireceğiz. İşte nasıl:

```csharp
// Ortaya çıkan belgenin ilk bölümünü açın.
Document sourceDoc = new Document(sourceDocumentPath);

// Sonuç olarak yeni bir belge oluşturun.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Belgeleri tek tek birleştirin.
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

### Aspose.Words for .NET kullanarak Belgeleri Birleştirme için örnek kaynak kodu

Aspose.Words for .NET'in Belgeleri Birleştir özelliğinin tam kaynak kodu burada:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Birleştirme için kullanarak belgeleri bulun.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Ortaya çıkan belgenin ilk bölümünü açın.
Document sourceDoc = new Document(sourceDocumentPath);

// Sonuç olarak yeni bir belge oluşturun.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Belge parçalarını birer birer birleştirin.
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
