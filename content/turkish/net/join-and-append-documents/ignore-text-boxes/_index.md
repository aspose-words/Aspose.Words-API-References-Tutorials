---
title: Metin Kutularını Yoksay
linktitle: Metin Kutularını Yoksay
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak metin kutusu formatını yok sayarak bir belgeye nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/ignore-text-boxes/
---

Bu eğitimde, metin kutularının formatını koruyarak bir belge eklemek için Aspose.Words for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, ekleme işlemi sırasında metin kutularını içerecek şekilde içe aktarma formatı seçeneklerinin nasıl ayarlanacağını gösterir.

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

## 3. Adım: İçe aktarma biçimi seçeneklerini ayarlayın

 Bir örneğini oluşturun`ImportFormatOptions`sınıfı seçin ve ayarlayın`IgnoreTextBoxes` mülkiyet`false`. Bu, metin kutularının biçimlendirmeleri korunarak ekleme işlemine dahil edilmesini sağlar.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## 4. Adım: Metin kutusu içeriğini ekleyin

 Oluşturmak`NodeImporter`nesnesini kullanın ve metin kutusu düğümlerini kaynak belgeden hedef belgeye aktarmak için kullanın. Kaynak belgedeki her paragrafı yineleyin ve bunu hedef belgeye aktarın.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## 5. Adım: Hedef belgeyi kaydedin

 Son olarak, değiştirilen hedef belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

Bu, Aspose.Words for .NET kullanarak metin kutusu formatını korurken belge ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Metin Kutularını Yoksay için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// İçe aktarırken kaynak metin kutularının formatını koruyun.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```