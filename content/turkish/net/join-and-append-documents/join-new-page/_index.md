---
title: Yeni Sayfaya Katılın
linktitle: Yeni Sayfaya Katılın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak formatı korurken iki belgeyi yeni bir sayfada nasıl birleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/join-new-page/
---

Bu eğitimde Aspose.Words for .NET kullanılarak iki belgenin yeni bir sayfada nasıl birleştirileceği açıklanmaktadır. Sağlanan kaynak kodu, eklenen belgeyi yeni bir sayfada başlatırken bir belgenin başka bir belgenin sonuna nasıl ekleneceğini gösterir.

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

## 3. Adım: Yeni sayfa bölümü başlangıcını ayarlayın

Eklenen belgeyi yeni bir sayfada başlatmak için`SectionStart` kaynak belgedeki ilk bölümün özelliği`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## 4. Adım: Kaynak belgeyi ekleyin

Kaynak belgeyi hedef belgeye şunu kullanarak ekleyin:`AppendDocument` yöntemi`Document` sınıf. İçe aktarma formatı modunu şu şekilde ayarlayın:`ImportFormatMode.KeepSourceFormatting` kaynak belgedeki orijinal stilleri korumak için.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. Adım: Değiştirilen belgeyi kaydedin

 Son olarak, değiştirilen hedef belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

Bu, Aspose.Words for .NET kullanarak iki belgeyi yeni bir sayfada birleştirme uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Yeni Sayfaya Katıl için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Eklenen belgeyi yeni bir sayfada başlayacak şekilde ayarlayın.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Kaynak belgede bulunan orijinal stilleri kullanarak kaynak belgeyi ekleyin.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```