---
title: Gömülü Windows Yazı Tiplerini Devre Dışı Bırak
linktitle: Gömülü Windows Yazı Tiplerini Devre Dışı Bırak
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile belgeleri PDF'ye dönüştürürken Windows yazı tipi gömmeyi nasıl devre dışı bırakacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

Bu eğitimde, Aspose.Words for .NET ile bir PDF belgesine Windows yazı tipi gömmeyi devre dışı bırakma adımlarında size yol göstereceğiz. Yazı tipi yerleştirmeyi devre dışı bırakarak oluşturulan PDF dosyasının boyutunu azaltabilirsiniz. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme

PDF'ye dönüştürmek istediğiniz belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Belgenize giden doğru yolu belirttiğinizden emin olun.

## 2. Adım: PDF kaydetme seçeneklerini ayarlayın

PdfSaveOptions sınıfının bir örneğini oluşturun ve yazı tiplerinin nasıl gömüleceğini belirtin:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Bu seçenek, oluşturulan PDF dosyasında Windows yazı tiplerinin entegrasyonunu devre dışı bırakmanıza olanak tanır.

## 3. Adım: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` dönüştürme seçeneklerini belirterek belgeyi PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Windows Yazı Tiplerini Gömmeyi Devre Dışı Bırakmak için örnek kaynak kodu

Aspose.Words for .NET ile Windows yazı tiplerini bir PDF belgesine gömmeyi devre dışı bırakmak için tam kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Çıktı PDF'si, standart Windows yazı tiplerini gömmeden kaydedilecektir.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Bu adımları izleyerek, Windows yazı tiplerinin Aspose.Words for .NET ile bir PDF belgesine gömülmesini kolayca devre dışı bırakabilirsiniz.

