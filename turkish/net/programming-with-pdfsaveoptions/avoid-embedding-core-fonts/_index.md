---
title: Çekirdek Yazı Tiplerini Gömmekten Kaçının
linktitle: Çekirdek Yazı Tiplerini Gömmekten Kaçının
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Word belgelerini PDF'ye dönüştürürken temel yazı tipi gömme işleminden nasıl kaçınacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

Bu eğitimde, Aspose.Words for .NET ile Temel Font Gömmesinden Kaçınma özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesi dönüştürülürken Arial, Times New Roman vb. gibi temel yazı tiplerinin PDF'ye gömülmesi gerekip gerekmediğini kontrol etmenizi sağlar. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme

PDF'ye dönüştürmek istediğiniz Word belgesini yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Word belgenizin doğru yolunu belirttiğinizden emin olun.

## 2. Adım: PDF Dönüştürme Seçeneklerini Ayarlayın

PdfSaveOptions sınıfının bir örneğini oluşturun ve temel yazı tipi katıştırmadan kaçınmayı etkinleştirin:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Bu seçenek, temel yazı tiplerinin PDF'ye gömülüp gömülmeyeceğini kontrol eder.

## 3. Adım: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` dönüştürme seçeneklerini belirterek Word belgesini PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Temel Yazı Tiplerini Gömmekten Kaçının için örnek kaynak kodu

Aspose.Words for .NET ile temel yazı tipi gömülmesini önlemek için özelliği kullanmak için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Çıktı PDF'si, Arial, Times New Roman vb. temel yazı tipleriyle gömülmeyecektir.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Bu adımları izleyerek, bir Word belgesini Aspose.Words for .NET ile dönüştürürken temel yazı tiplerinin PDF'ye gömülmesi gerekip gerekmediğini kolayca kontrol edebilirsiniz.

