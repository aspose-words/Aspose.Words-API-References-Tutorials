---
title: Pdf'ye Dönüştürme 17
linktitle: Pdf'ye Dönüştürme 17
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile belgeleri PDF 1.7'ye nasıl dönüştüreceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

Bu eğitimde, Aspose.Words for .NET ile PDF 1.7'ye dönüştürme adımlarında size yol göstereceğiz. PDF 1.7'ye dönüştürmek, PDF 1.7 standardına uygun PDF dosyaları oluşturmanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme

PDF'ye dönüştürmek istediğiniz belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Belgenize giden doğru yolu belirttiğinizden emin olun.

## 2. Adım: PDF Dönüştürme Seçeneklerini Ayarlayın

PdfSaveOptions sınıfının bir örneğini oluşturun ve kullanmak istediğiniz PDF standardının sürümünü belirtin:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Bu seçenek, oluşturulan PDF dosyasının PDF 1.7 standardına uygun olmasını sağlar.

## 3. Adım: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` dönüştürme seçeneklerini belirterek belgeyi PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak PDF 17'ye Dönüştürme için örnek kaynak kodu

Aspose.Words for .NET ile PDF 1.7'ye dönüştürmek için kaynak kodun tamamı burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

Bu adımları izleyerek Aspose.Words for .NET ile kolayca PDF 1.7'ye dönüştürebilirsiniz.

