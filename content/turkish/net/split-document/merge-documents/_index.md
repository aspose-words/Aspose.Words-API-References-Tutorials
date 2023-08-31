---
title: Word Belgelerini Birleştir
linktitle: Belgeleri Birleştir
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak birden fazla Word belgesini nasıl birleştireceğinizi öğrenin. Bu güçlü API, belgeleri birleştirme sürecini basitleştirerek verimli ve basit hale getirir.
type: docs
weight: 10
url: /tr/net/split-document/merge-documents/
---

Bu eğitimde, Aspose.Words for .NET'in Belgeleri Birleştir özelliğini kullanarak birden fazla Word belgesini nasıl birleştireceğinizi anlatacağız. Kaynak kodunu anlamak ve tüm kaynak belgeleri içeren birleştirilmiş bir belge elde etmek için aşağıdaki adımları izleyin.

## 1. Adım: Birleştirilecek belgeleri arayın

Belgeleri birleştirmeden önce birleştirilecek kaynak belgeleri bulmamız gerekiyor. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Birleştirilecek belgeleri arayın.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## 2. Adım: Belgeleri birleştirin

Şimdi nihai birleştirilmiş belge oluşturmak için belgeleri tek tek birleştireceğiz. İşte nasıl:

```csharp
// Ortaya çıkan belgenin ilk bölümünü açın.
Document sourceDoc = new Document(sourceDocumentPath);

// Ortaya çıkan yeni bir belge oluşturun.
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

Aspose.Words for .NET'in Belgeleri Birleştir özelliğinin tam kaynak kodu:

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

// Ortaya çıkan yeni bir belge oluşturun.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Belge parçalarını tek tek birleştirin.
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

## Çözüm

Tebrikler! Aspose.Words for .NET'in Belgeleri Birleştir özelliğini kullanarak birden fazla Word belgesini nasıl birleştireceğinizi öğrendiniz. Sağlanan kaynak kodunu takip ederek, her kaynak belgenin formatını korurken ayrı belgeleri tek bir birleştirilmiş belgede birleştirebilirsiniz.

Birden çok kaynaktan gelen bilgileri birleştirmek veya tek tek parçalardan birleşik bir belge oluşturmak istediğinizde belgeleri birleştirmek yararlı olabilir. Aspose.Words for .NET, belgeleri birleştirme işlemini basitleştirerek verimli ve basit hale getiren güçlü bir API sağlar.

Belge işleme yeteneklerinizi geliştirmek ve iş akışınızı kolaylaştırmak için Aspose.Words for .NET tarafından sunulan diğer özellikleri keşfetmekten çekinmeyin.

### SSS

#### Farklı biçimlendirmeye sahip belgeleri nasıl birleştirebilirim?

 Aspose.Words for .NET, belgeleri birleştirirken her kaynak belgenin formatını koruma seçeneğini sunar. kullanarak`ImportFormatMode.KeepSourceFormatting` seçeneğini seçerseniz, birleştirilen belge orijinal belgelerin biçimlendirmesini koruyacaktır. Birleştirilen belgenin tamamında tutarlı formatlama uygulamak istiyorsanız, belgeleri birleştirdikten sonra Aspose.Words API'sini kullanarak formatı değiştirebilirsiniz.

#### Farklı formatlardaki belgeleri birleştirebilir miyim?

Evet, Aspose.Words for .NET, DOCX, DOC, RTF ve daha fazlası dahil olmak üzere çeşitli formatlardaki belgelerin birleştirilmesini destekler. Aspose.Words API'sine farklı formatlardaki belgeleri yükleyebilir ve orijinal formatlarına bakılmaksızın bunları tek bir belgede birleştirebilirsiniz.

#### Tablolar ve resimler gibi karmaşık yapılara sahip belgeleri birleştirebilir miyim?

Kesinlikle! Aspose.Words for .NET; tablolar, resimler, üstbilgiler, altbilgiler ve daha fazlasını içeren karmaşık yapılara sahip belgeleri birleştirme yeteneğine sahiptir. API, her belgedeki içeriğin bütünlüğünü ve düzenini korurken birleştirme işlemini gerçekleştirir.

#### Farklı sayfa yönelimlerine veya boyutlarına sahip belgeleri birleştirmek mümkün müdür?

Evet, Aspose.Words for .NET, birleştirme işlemi sırasında farklı sayfa yönelimlerine veya boyutlarına sahip belgeleri işler. Ortaya çıkan birleştirilmiş belge, kaynak belgelerin değişen sayfa yönelimlerine ve boyutlarına uyum sağlayacaktır.