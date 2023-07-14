---
title: Belge Ekle
linktitle: Belge Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir belgenin içeriğini diğerine nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/append-document/
---

Bu eğitim, bir belgenin içeriğini diğerine eklemek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, kaynak ve hedef belgelerin nasıl açılacağını, kaynak belgeden bölümlerin nasıl alınacağını ve hedef belgeye nasıl ekleneceğini gösterir.

## 1. Adım: Projeyi kurun

Aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı yüklendi. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet paket yöneticisini kullanabilirsiniz.
- Kaynak ve hedef belgelerin bulunduğu bir belge dizini yolu.

## 2. Adım: Kaynak ve hedef belgeleri açın

 kullanarak kaynak ve hedef belgeleri açın.`Document` sınıf oluşturucu Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: Kaynak belgeden hedef belgeye bölümler ekleyin

 Kaynak belgedeki tüm bölümler arasında dolaşın ve her bölümü hedef belgeye içe aktarın.`ImportNode` yöntem. Ardından, içe aktarılan bölümü hedef belgeye ekleyin.

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

Bu, Aspose.Words for .NET kullanarak belge ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Append Document için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Kaynak belgedeki tüm bölümler arasında geçiş yapın.
	// Bölüm düğümleri, Belge düğümünün doğrudan çocuklarıdır, bu nedenle Belgeyi numaralandırabiliriz.
	foreach (Section srcSection in srcDoc)
	{
		// Bir bölümü bir belgeden diğerine kopyaladığımız için,
		// Bölüm düğümünü hedef belgeye aktarmak gerekir.
		// Bu, stillere, listelere vb. belgeye özgü referansları ayarlar.
		//
		// Bir düğümün içe aktarılması, orijinal düğümün bir kopyasını oluşturur, ancak kopya
		// hedef belgeye eklenmeye hazır.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Artık yeni bölüm düğümü hedef belgeye eklenebilir.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```