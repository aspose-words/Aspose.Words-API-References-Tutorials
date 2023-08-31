---
title: Üstbilgi Altbilgisini Yoksay
linktitle: Üstbilgi Altbilgisini Yoksay
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak üstbilgi ve altbilgi içeriğini göz ardı ederek bir belgeye nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/ignore-header-footer/
---

Bu eğitimde, üstbilgi ve altbilgi içeriğini göz ardı ederek bir belge eklemek için Aspose.Words for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, ekleme işlemi sırasında üstbilgi ve altbilgiyi hariç tutmak için içe aktarma formatı seçeneklerinin nasıl ayarlanacağını gösterir.

## 1. Adım: Projeyi ayarlayın

Aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kütüphanesi kuruldu. Şuradan indirebilirsiniz[Aspose.Releases]https://releases.aspose.com/words/net/ adresine gidin veya yüklemek için NuGet paket yöneticisini kullanın.
- Kaynak ve hedef belgelerin bulunduğu belge dizini yolu.

## 2. Adım: Kaynak ve hedef belgeleri açın

 Kaynak ve hedef belgeleri kullanarak açın.`Document` sınıf yapıcısı. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: İçe aktarma biçimi seçeneklerini ayarlayın

 Bir örneğini oluşturun`ImportFormatOptions`sınıfı seçin ve ayarlayın`IgnoreHeaderFooter` mülkiyet`false`. Bu, ekleme işlemi sırasında üstbilgi ve altbilgi içeriğinin dahil edilmesini sağlar.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## 4. Adım: Kaynak belgeyi hedef belgeye ekleyin

 Kullan`AppendDocument`Kaynak belgenin ekleneceği hedef belgenin yöntemi. Geçmek`ImportFormatMode.KeepSourceFormatting` ikinci parametre olarak içe aktarma formatı seçeneklerini ve üçüncü parametre olarak içe aktarma formatı seçeneklerini seçin.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## 5. Adım: Hedef belgeyi kaydedin

 Son olarak, değiştirilen hedef belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Bu, Aspose.Words for .NET kullanarak üstbilgi ve altbilgi içeriğini göz ardı ederek belge ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Üst Bilgi Alt Bilgisini Yoksay için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```