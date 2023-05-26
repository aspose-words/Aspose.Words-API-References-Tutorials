---
title: Katıştırılmış Alt Küme Yazı Tipleri
linktitle: Katıştırılmış Alt Küme Yazı Tipleri
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak yazı tipi altkümelerini bir PDF'ye gömmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Bu makale, yazı tipi alt kümesi gömme özelliğinin Aspose.Words for .NET ile nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, yazı tiplerinin alt kümelerini bir belgeye nasıl gömeceğinizi ve yalnızca belgede kullanılan glifleri içeren bir PDF oluşturmayı öğrenebileceksiniz.

Başlamadan önce, projenizde Aspose.Words for .NET kitaplığını kurduğunuzdan ve yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için, belgelerinizin bulunduğu dizine giden yolu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler dizininize giden gerçek yolla.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Ardından, işlemek istediğimiz belgeyi yüklememiz gerekiyor. Bu örnekte, belgenin "Rendering.docx" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: PDF olarak kaydetme seçeneklerini yapılandırın

 Yalnızca belgede kullanılan yazı tiplerinin alt kümelerini içeren bir PDF oluşturmak için,`PdfSaveOptions` ile nesne`EmbedFullFonts` özellik ayarlandı`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## 4. Adım: Belgeyi yazı tipi alt kümeleriyle PDF olarak kaydedin

 Son olarak, yazı tipi alt kümelerini kullanarak belgeyi PDF olarak kaydedebiliriz. Çıktı dosyası adını ve`saveOptions` önceki adımda yapılandırdığımız nesne.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Bu kadar ! Yazı tiplerinin alt kümelerini bir belgeye başarıyla gömdünüz ve Aspose.Words for .NET ile yalnızca belgede kullanılan glifleri içeren bir PDF oluşturdunuz.

### Aspose.Words for .NET ile yazı tipi alt kümelerini gömmek için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Çıktı PDF'si, belgedeki yazı tiplerinin alt kümelerini içerecektir.
	// PDF yazı tiplerine yalnızca belgede kullanılan glifler dahildir.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```
