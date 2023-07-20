---
title: Farklı Sayfa Düzeni
linktitle: Farklı Sayfa Düzeni
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak farklı sayfa düzeni ayarlarına sahip bir belgeyi nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/different-page-setup/
---

Bu öğretici, farklı sayfa düzeni ayarlarına sahip bir belgeyi başka bir belgeye eklemek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, kaynak ve hedef belgeler için farklı sayfa ayarlarının nasıl ayarlanacağını ve düzgün devam ve numaralandırmanın nasıl sağlanacağını gösterir.

## 1. Adım: Projeyi kurun

Aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı yüklendi. adresinden indirebilirsiniz[Aspose.Releases]https://releases.aspose.com/words/net/ veya yüklemek için NuGet paket yöneticisini kullanın.
- Kaynak ve hedef belgelerin bulunduğu bir belge dizini yolu.

## 2. Adım: Kaynak ve hedef belgeleri açın

 kullanarak kaynak ve hedef belgeleri açın.`Document` sınıf oluşturucu Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: Kaynak belge için sayfa ayarlarını yapın

Düzgün devam ve numaralandırmayı sağlamak için kaynak belgenin sayfa düzeni ayarlarını düzenleyin. Bu örnekte, bölümün başlangıcını şu şekilde ayarladık:`SectionStart.Continuous` ve sayfa numaralandırmayı yeniden başlatın. Ayrıca sayfa genişliğinin, yüksekliğinin ve yönünün hedef belgenin son bölümüyle eşleştiğinden emin oluruz.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## 4. Adım: Paragraf biçimlendirmesini değiştirin

 Doğru biçimlendirmeyi sürdürmek için, kaynak belgedeki tüm paragrafları yineleyin ve`KeepWithNext` mülkiyet`true`. Bu, ekleme işlemi sırasında paragrafların bir arada kalmasını sağlar.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Adım 5: Kaynak belgeyi hedef belgeye ekleyin

 Kullan`AppendDocument` kaynak biçimlendirmesini koruyarak, değiştirilen kaynak belgeyi hedef belgeye eklemek için hedef belgenin yöntemi.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6. Adım: Hedef belgeyi kaydedin

 Son olarak, değiştirilen hedef belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Bu, Aspose.Words for .NET kullanılarak farklı sayfa düzeni ayarlarına sahip bir belgenin eklenmesi uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Farklı Sayfa Düzeni için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Kaynak belgeyi, hedef belgenin bitiminden hemen sonra devam edecek şekilde ayarlayın.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Kaynak belgenin başlangıcında sayfa numaralandırmayı yeniden başlatın.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// Kaynak belgede farklı sayfa düzeni ayarları olduğunda bunun olmamasını sağlamak için,
	// ayarlar, hedef belgenin son bölümü arasında aynıdır.
	// Kaynak belgede devam eden başka sürekli bölümler varsa,
	// bunun o bölümler için tekrarlanması gerekecektir.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Kaynak belgedeki tüm bölümleri yineleyin.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```