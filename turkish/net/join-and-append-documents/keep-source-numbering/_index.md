---
title: Kaynak Numaralandırmayı Koru
linktitle: Kaynak Numaralandırmayı Koru
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET'te kaynak numaralandırma biçimlendirmesini korurken bir belgeyi nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/keep-source-numbering/
---

Bu öğretici, Aspose.Words for .NET kullanılarak numaralı paragrafların orijinal numaralandırma biçimlendirmesini korurken bir kaynak belgeyi bir hedef belgeye nasıl ekleyeceğinizi açıklar.

## 1. Adım: Projeyi kurun

Aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı yüklendi. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet paket yöneticisini kullanabilirsiniz.
- Kaynak ve hedef belgelerin kaydedileceği bir belge dizini yolu.

## 2. Adım: Hedef ve kaynak belgeleri oluşturun

 Örneklerini oluştur`Document` hedef ve kaynak belgeler için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: İçe aktarırken kaynak numaralandırmayı koruyun

 Kaynak belgedeki numaralandırılmış paragrafların numaralandırma biçimlendirmesini korumak için bir örnek oluşturun.`ImportFormatOptions` ve ayarla`KeepSourceNumbering` ile`true` . Kullanın`NodeImporter` kaynak belgeden hedef belgeye düğümleri içe aktarmak için`ImportFormatMode.KeepSourceFormatting` ve`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## 4. Adım: Paragrafları içe aktarın ve ekleyin

 Kaynak belgedeki paragrafları yineleyin ve her paragrafı hedef belgeye aktarın.`importer`. İçe aktarılan düğümleri hedef belgenin gövdesine ekleyin.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## 5. Adım: Değiştirilen belgeyi kaydedin

 Değiştirilen belgeyi şunu kullanarak kaydedin:`Save` yöntemi`Document` nesne.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Bu, Aspose.Words for .NET kullanarak orijinal numaralandırma biçimlendirmesini korurken bir kaynak belgeyi hedef belgeye ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Keep Source Numbering için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Numaralandırılmış paragrafları içe aktarırken kaynak listesi biçimlendirmesini koruyun.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```