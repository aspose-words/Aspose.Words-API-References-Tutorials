---
title: Üstbilgi Altbilgiyi Yoksay
linktitle: Üstbilgi Altbilgiyi Yoksay
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak üstbilgi ve altbilgi içeriğini yok sayarken bir belgeyi nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/ignore-header-footer/
---

Bu öğretici, üstbilgi ve altbilgi içeriğini yok sayarak bir belgeyi eklemek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, ekleme işlemi sırasında üstbilgi ve altbilgiyi hariç tutmak için içe aktarma biçimi seçeneklerinin nasıl ayarlanacağını gösterir.

## 1. Adım: Projeyi kurun

Aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı yüklendi. adresinden indirebilirsiniz[Aspose.Releases]https://releases.aspose.com/words/net/ veya yüklemek için NuGet paket yöneticisini kullanın.
- Kaynak ve hedef belgelerin bulunduğu bir belge dizini yolu.

## 2. Adım: Kaynak ve hedef belgeleri açın

 kullanarak kaynak ve hedef belgeleri açın.`Document` sınıf oluşturucu Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: İçe aktarma biçimi seçeneklerini ayarlayın

 örneğini oluşturun`ImportFormatOptions`sınıflandırın ve ayarlayın`IgnoreHeaderFooter` mülkiyet`false`. Bu, üstbilgi ve altbilgi içeriğinin ekleme işlemi sırasında dahil edilmesini sağlar.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## 4. Adım: Kaynak belgeyi hedef belgeye ekleyin

 Kullan`AppendDocument`kaynak belgeyi eklemek için hedef belgenin yöntemi. Geçmek`ImportFormatMode.KeepSourceFormatting` ikinci parametre olarak ve içe aktarma biçimi seçeneklerini üçüncü parametre olarak.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## 5. Adım: Hedef belgeyi kaydedin

 Son olarak, değiştirilen hedef belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Bu, Aspose.Words for .NET kullanarak üst bilgi ve alt bilgi içeriğini yok sayarak belge ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Üstbilgi Altbilgiyi Yoksay için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```