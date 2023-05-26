---
title: Metin Kutularını Yoksay
linktitle: Metin Kutularını Yoksay
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak metin kutusu biçimlendirmesini yok sayarken bir belgeyi nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/ignore-text-boxes/
---

Bu eğitim, metin kutularının biçimlendirmesini korurken bir belgeyi eklemek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, ekleme işlemi sırasında metin kutularını dahil etmek için içe aktarma biçimi seçeneklerinin nasıl ayarlanacağını gösterir.

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

## 3. Adım: İçe aktarma biçimi seçeneklerini ayarlayın

 örneğini oluşturun`ImportFormatOptions` sınıflandırın ve ayarlayın`IgnoreTextBoxes` mülkiyet`false`. Bu, metin kutularının biçimlendirmeleri korunurken ekleme işlemi sırasında dahil edilmesini sağlar.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## 4. Adım: Metin kutusu içeriğini ekleyin

 Oluşturmak`NodeImporter` nesneyi seçin ve metin kutusu düğümlerini kaynak belgeden hedef belgeye içe aktarmak için kullanın. Kaynak belgedeki her paragrafı yineleyin ve onu hedef belgeye aktarın.

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

Bu, Aspose.Words for .NET kullanarak metin kutusu biçimlendirmesini korurken belge ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Metin Kutularını Yoksay için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//İçe aktarırken kaynak metin kutularının biçimlendirmesini koruyun.
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