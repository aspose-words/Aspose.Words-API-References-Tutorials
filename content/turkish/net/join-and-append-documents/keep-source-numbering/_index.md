---
title: Kaynak Numaralandırmasını Koruyun
linktitle: Kaynak Numaralandırmasını Koruyun
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'te kaynak numaralandırma formatını korurken bir belgeye nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/keep-source-numbering/
---

Bu eğitimde, Aspose.Words for .NET kullanılarak numaralı paragrafların orijinal numaralandırma formatı korunarak bir kaynak belgenin hedef belgeye nasıl ekleneceği açıklanmaktadır.

## 1. Adım: Projeyi ayarlayın

Aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET kütüphanesi kuruldu. Şuradan indirebilirsiniz[Aspose.Releases]https://releases.aspose.com/words/net/ adresine gidin veya yüklemek için NuGet paket yöneticisini kullanın.
- Kaynak ve hedef belgelerin kaydedileceği belge dizini yolu.

## 2. Adım: Hedef ve kaynak belgeleri oluşturun

 Örneklerini oluştur`Document` Hedef ve kaynak belgeler için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: İçe aktarırken kaynak numaralandırmayı koruyun

 Kaynak belgedeki numaralandırılmış paragrafların numaralandırma formatını korumak için,`ImportFormatOptions` ve ayarla`KeepSourceNumbering` ile`true` . Kullanın`NodeImporter` Düğümleri kaynak belgeden hedef belgeye aktarmak için şunları belirterek`ImportFormatMode.KeepSourceFormatting` ve`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## 4. Adım: Paragrafları içe aktarın ve ekleyin

Kaynak belgedeki paragraflar arasında yineleyin ve her paragrafı hedef belgeye aktarın.`importer`. İçe aktarılan düğümleri hedef belgenin gövdesine ekleyin.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## 5. Adım: Değiştirilen belgeyi kaydedin

 Değiştirilen belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Bu, Aspose.Words for .NET kullanarak orijinal numaralandırma formatını korurken, kaynak belgenin hedef belgeye eklenmesi uygulamasını tamamlıyor.

### Aspose.Words for .NET kullanarak Kaynak Numaralandırmayı Koru için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Numaralandırılmış paragrafları içe aktarırken kaynak listesi formatını koruyun.
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