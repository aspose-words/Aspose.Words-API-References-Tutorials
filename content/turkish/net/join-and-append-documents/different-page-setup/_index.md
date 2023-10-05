---
title: Farklı Sayfa Düzeni
linktitle: Farklı Sayfa Düzeni
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak farklı sayfa düzeni ayarlarıyla bir belgeyi nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/different-page-setup/
---

Bu eğitimde, farklı sayfa yapısı ayarlarına sahip bir belgeyi başka bir belgeye eklemek için Aspose.Words for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, kaynak ve hedef belgeler için farklı sayfa ayarlarının nasıl ayarlanacağını ve düzgün devam ve numaralandırmanın nasıl sağlanacağını gösterir.

## 1. Adım: Projeyi ayarlayın

Aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET kütüphanesi kuruldu. Şuradan indirebilirsiniz[Aspose.Releases]https://releases.aspose.com/words/net/ adresine gidin veya yüklemek için NuGet paket yöneticisini kullanın.
- Kaynak ve hedef belgelerin bulunduğu belge dizini yolu.

## 2. Adım: Kaynak ve hedef belgeleri açın

 Kaynak ve hedef belgeleri kullanarak açın.`Document` sınıf yapıcısı. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: Kaynak belge için sayfa ayarlarını yapın

 Devamın ve numaralandırmanın doğru olmasını sağlamak için kaynak belgenin sayfa düzeni ayarlarını yapın. Bu örnekte bölümün başlangıcını şu şekilde ayarladık:`SectionStart.Continuous` ve sayfa numaralandırmayı yeniden başlatın. Ayrıca sayfa genişliğinin, yüksekliğinin ve yönünün hedef belgenin son bölümüyle eşleştiğinden de emin oluruz.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## 4. Adım: Paragraf biçimlendirmesini değiştirin

 Doğru biçimlendirmeyi korumak için kaynak belgedeki tüm paragrafları yineleyin ve`KeepWithNext`mülkiyet`true`Bu, ekleme işlemi sırasında paragrafların bir arada kalmasını sağlar.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Adım 5: Kaynak belgeyi hedef belgeye ekleyin

 Kullan`AppendDocument` Kaynak formatını koruyarak, değiştirilen kaynak belgeyi hedef belgeye eklemek için hedef belgenin yöntemi.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6. Adım: Hedef belgeyi kaydedin

 Son olarak, değiştirilen hedef belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Bu, Aspose.Words for .NET kullanılarak farklı sayfa yapısı ayarlarına sahip bir belgenin eklenmesi uygulamasını tamamlar.

### Aspose.Words for .NET kullanılarak Farklı Sayfa Düzeni için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Kaynak belgeyi, hedef belgenin bitiminden hemen sonra devam edecek şekilde ayarlayın.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Kaynak belgenin başlangıcındaki sayfa numaralandırmasını yeniden başlatın.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// Kaynak belgenin farklı sayfa yapısı ayarları olduğunda bunun oluşmamasını sağlamak için,
	// ayarlar hedef belgenin son bölümü arasında aynıdır.
	// Kaynak belgede devam eden başka sürekli bölümler varsa,
	//bu bölümler için bunun tekrarlanması gerekecektir.
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