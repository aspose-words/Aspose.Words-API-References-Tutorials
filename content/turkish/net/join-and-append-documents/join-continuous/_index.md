---
title: Sürekli Katıl
linktitle: Sürekli Katıl
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak biçimlendirmeyi korurken iki belgeyi sürekli olarak nasıl birleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/join-continuous/
---

Bu eğitimde Aspose.Words for .NET kullanılarak iki belgenin sürekli olarak nasıl birleştirileceği açıklanmaktadır. Sağlanan kaynak kodu, orijinal biçimlendirmeyi korurken bir belgenin başka bir belgenin sonuna nasıl ekleneceğini gösterir.

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

## 3. Adım: Sürekli bölüm başlangıcını ayarlayın

Kaynak belgenin hedef belgenin içeriğinden hemen sonra görünmesini sağlamak için`SectionStart` kaynak belgedeki ilk bölümün özelliği`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 4. Adım: Kaynak belgeyi ekleyin

 Kaynak belgeyi hedef belgeye şunu kullanarak ekleyin:`AppendDocument` yöntemi`Document` sınıf. İçe aktarma formatı modunu şu şekilde ayarlayın:`ImportFormatMode.KeepSourceFormatting` kaynak belgedeki orijinal stilleri korumak için.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. Adım: Değiştirilen belgeyi kaydedin

 Son olarak, değiştirilen hedef belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

Bu, Aspose.Words for .NET kullanarak iki belgenin sürekli olarak birleştirilmesi uygulamasını tamamlıyor.

### Aspose.Words for .NET kullanarak join Continuous için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Belgenin hedef belge içeriğinden hemen sonra görünmesini sağlayın.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Kaynak belgede bulunan orijinal stilleri kullanarak kaynak belgeyi ekleyin.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```