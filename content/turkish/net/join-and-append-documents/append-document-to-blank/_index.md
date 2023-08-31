---
title: Belgeyi Boşluğa Ekle
linktitle: Belgeyi Boşluğa Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'te boş bir hedef belgeye nasıl belge ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/append-document-to-blank/
---

Bu eğitimde, bir belgenin içeriğini boş bir hedef belgeye eklemek için Aspose.Words for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, yeni bir belgenin nasıl oluşturulacağını, içeriğinin nasıl kaldırılacağını ve ardından kaynak belgenin ona nasıl ekleneceğini gösterir.

## 1. Adım: Projeyi ayarlayın

Aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kütüphanesi kuruldu. Şuradan indirebilirsiniz[Aspose.Releases]https://releases.aspose.com/words/net/ adresine gidin veya yüklemek için NuGet paket yöneticisini kullanın.
- Kaynak ve hedef belgelerin bulunduğu belge dizini yolu.

## 2. Adım: Yeni bir hedef belge oluşturun

 Yeni bir tane oluştur`Document` Hedef belge için nesne.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## 3. Adım: Mevcut içeriği hedef belgeden kaldırın

 Temiz bir hedef belge elde etmek için, mevcut tüm içeriği belgeden kaldırın.`RemoveAllChildren` yöntem.

```csharp
dstDoc.RemoveAllChildren();
```

## 4. Adım: Kaynak belgeyi hedef belgeye ekleyin

 Kaynak belgenin içeriğini hedef belgeye şunu kullanarak ekleyin:`AppendDocument` ile yöntem`ImportFormatMode.KeepSourceFormatting` seçenek.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. Adım: Hedef belgeyi kaydedin

 Son olarak, değiştirilen hedef belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Bu, Aspose.Words for .NET kullanarak bir belgenin boş bir hedef belgeye eklenmesi uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Belgeyi Boşluğa Ekleme için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	//Hedef belge boş değildir ve genellikle eklenen belgeden önce boş bir sayfanın görünmesine neden olur.
	// Bunun nedeni, temel belgenin boş bir bölüme sahip olması ve yeni belgenin bir sonraki sayfada başlatılmasıdır.
	// Eklemeden önce hedef belgedeki tüm içeriği kaldırın.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```