---
title: Belge Ekle
linktitle: Belge Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak bir belgenin içeriğini diğerine nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/append-document/
---

Bu eğitimde Aspose.Words for .NET'in bir belgenin içeriğini diğerine eklemek için nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, kaynak ve hedef belgelerin nasıl açılacağını, kaynak belgeden bölümlerin hedef belgeye nasıl aktarılacağını ve ekleneceğini gösterir.

## 1. Adım: Projeyi ayarlayın

Aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kütüphanesi kuruldu. Şuradan indirebilirsiniz[Aspose.Releases]https://releases.aspose.com/words/net/ adresine gidin veya yüklemek için NuGet paket yöneticisini kullanın.
- Kaynak ve hedef belgelerin bulunduğu belge dizini yolu.

## 2. Adım: Kaynak ve hedef belgeleri açın

 Kaynak ve hedef belgeleri kullanarak açın.`Document` sınıf yapıcısı. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: Kaynak belgedeki bölümleri hedef belgeye ekleyin

 Kaynak belgedeki tüm bölümler arasında dolaşın ve her bölümü hedef belgeye aktarın.`ImportNode` yöntem. Daha sonra içe aktarılan bölümü hedef belgeye ekleyin.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## 4. Adım: Hedef belgeyi kaydedin

 Son olarak, değiştirilen hedef belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

Bu, Aspose.Words for .NET kullanarak belge ekleme işlemini tamamlar.

### Aspose.Words for .NET kullanarak Belge Ekleme için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Kaynak belgedeki tüm bölümler arasında dolaşın.
	// Bölüm düğümleri Belge düğümünün doğrudan alt öğeleridir, dolayısıyla Belgeyi yalnızca numaralandırabiliriz.
	foreach (Section srcSection in srcDoc)
	{
		// Bir bölümü bir belgeden diğerine kopyaladığımız için,
		// Bölüm düğümünün hedef belgeye aktarılması gerekir.
		// Bu, stillere, listelere vb. yönelik belgeye özgü referansları ayarlar.
		//
		// Bir düğümün içe aktarılması orijinal düğümün bir kopyasını oluşturur, ancak kopya
		// Hedef belgeye eklenmeye hazır ss.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Artık yeni bölüm düğümü hedef belgeye eklenebilir.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```