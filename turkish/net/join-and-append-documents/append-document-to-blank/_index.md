---
title: Belgeyi Boşluğa Ekle
linktitle: Belgeyi Boşluğa Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET'te bir belgeyi boş bir hedef belgeye nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/append-document-to-blank/
---

Bu eğitim, bir belgenin içeriğini boş bir hedef belgeye eklemek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, yeni bir belgenin nasıl oluşturulacağını, içeriğinin nasıl kaldırılacağını ve ardından kaynak belgenin buna nasıl ekleneceğini gösterir.

## 1. Adım: Projeyi kurun

Aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı yüklendi. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet paket yöneticisini kullanabilirsiniz.
- Kaynak ve hedef belgelerin bulunduğu bir belge dizini yolu.

## 2. Adım: Yeni bir hedef belge oluşturun

 Yeni bir tane oluştur`Document` hedef belge için nesne.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## 3. Adım: Mevcut içeriği hedef belgeden kaldırın

 Temiz bir hedef belge sağlamak için, mevcut tüm içeriği belgeden kaldırın.`RemoveAllChildren` yöntem.

```csharp
dstDoc.RemoveAllChildren();
```

## 4. Adım: Kaynak belgeyi hedef belgeye ekleyin

 kullanarak kaynak belgenin içeriğini hedef belgeye ekleyin.`AppendDocument` ile yöntem`ImportFormatMode.KeepSourceFormatting` seçenek.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. Adım: Hedef belgeyi kaydedin

 Son olarak, değiştirilen hedef belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Bu, Aspose.Words for .NET kullanılarak boş bir hedef belgeye belge ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Belgeyi Boşluğa Ekleme için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	//Hedef belge boş değil, genellikle eklenen belgeden önce boş bir sayfanın görünmesine neden oluyor.
	// Bunun nedeni, temel belgede boş bir bölümün olması ve yeni belgenin bir sonraki sayfada başlatılmasıdır.
	// Eklemeden önce hedef belgedeki tüm içeriği kaldırın.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```