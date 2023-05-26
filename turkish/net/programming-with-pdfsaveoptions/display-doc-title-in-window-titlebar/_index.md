---
title: Belge Başlığını Pencere Başlık Çubuğunda Görüntüle
linktitle: Belge Başlığını Pencere Başlık Çubuğunda Görüntüle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile PDF'ye dönüştürürken belge başlığını pencere başlık çubuğunda nasıl görüntüleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

Bu öğreticide, Aspose.Words for .NET ile belge başlığını pencere başlık çubuğunda görüntüleme adımlarında size rehberlik edeceğiz. Bu özellik, oluşturulan PDF belgesini açtığınızda belge başlığını pencere başlık çubuğunda görüntülemenizi sağlar. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme

PDF'ye dönüştürmek istediğiniz belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Belgenize giden doğru yolu belirttiğinizden emin olun.

## 2. Adım: PDF Kaydetme Seçeneklerini Yapılandırın

PdfSaveOptions sınıfının bir örneğini oluşturun ve belge başlığının pencere başlık çubuğunda görüntülenmesini etkinleştirin:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

Bu seçenek, PDF'ye dönüştürürken belge başlığının pencere başlık çubuğunda görüntülenmesini sağlar.

## 3. Adım: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` dönüştürme seçeneklerini belirterek belgeyi PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Belge Başlığını Pencere Başlık Çubuğunda Göster için örnek kaynak kodu

Aspose.Words for .NET ile bir PDF belgesinde belge başlığını pencere başlık çubuğunda görüntülemek için tam kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
Bu adımları izleyerek, Aspose.Words for .NET ile PDF'ye dönüştürürken belge başlığını pencere başlık çubuğunda kolayca görüntüleyebilirsiniz.

