---
title: Gömülü Tüm Yazı Tipleri
linktitle: Gömülü Tüm Yazı Tipleri
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak tüm yazı tiplerini bir PDF'ye gömmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/embedded-all-fonts/
---

Bu makale, Aspose.Words for .NET'in Gömülü Tüm Yazı Tipleri özelliğinin nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kod parçacığını inceleyeceğiz ve her bir parçayı ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak tüm yazı tiplerini bir belgeye nasıl gömeceğinizi ve gömülü yazı tipleriyle bir PDF oluşturmayı öğrenebileceksiniz.

Başlamadan önce, projenizde Aspose.Words for .NET kitaplığının kurulu ve ayarlanmış olduğundan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizini yolunu tanımlayın

Başlamak için, belgelerinizin bulunduğu dizinin yolunu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Ardından, işlemek istediğimiz belgeyi yüklememiz gerekiyor. Bu örnekte, belgenin "Rendering.docx" olarak adlandırıldığını ve belirtilen belge dizininde bulunduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: PDF kaydetme seçeneklerini yapılandırın

 Ortaya çıkan PDF'e tüm yazı tiplerini gömmek için,`PdfSaveOptions` ile nesne`EmbedFullFonts` özellik ayarlandı`true`. Bu, belgede kullanılan tüm yazı tiplerinin oluşturulan PDF dosyasına dahil edilmesini sağlar.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
```

## 4. Adım: Belgeyi katıştırılmış yazı tipleriyle PDF olarak kaydedin

 Son olarak, belgeyi gömülü yazı tipleriyle bir PDF dosyası olarak kaydedebiliriz. Çıktı dosyası adını belirtin ve`saveOptions` önceki adımda yapılandırdığımız nesne.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
```

Bu kadar! Tüm yazı tiplerini bir belgeye başarıyla gömdünüz ve Aspose.Words for .NET kullanarak gömülü yazı tipleriyle bir PDF oluşturdunuz.

### Aspose.Words for .NET kullanan Embedded All Fonts için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Çıktı PDF'si, belgede bulunan tüm yazı tipleriyle gömülecektir.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
  
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET'in Gömülü Tüm Yazı Tipleri özelliğini adım adım kullanma sürecini ele aldık. Belge yüklemeyi, PDF kaydetme seçeneklerini yapılandırmayı ve belgeyi katıştırılmış yazı tipleriyle PDF dosyası olarak kaydetmeyi öğrendik. Bu kılavuzu takip ederek, farklı aygıtlar ve platformlar arasında tutarlı ve doğru işleme sağlayarak, PDF belgelerinizde gerekli tüm yazı tiplerinin gömülü olduğundan emin olabilirsiniz.
