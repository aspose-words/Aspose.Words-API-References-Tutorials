---
title: Gömülü Arial ve Times Roman Yazı Tiplerini Atla
linktitle: Gömülü Arial ve Times Roman Yazı Tiplerini Atla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Arial ve Times Roman yazı tiplerini gömmeden PDF oluşturmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Bu makale, gömülü Arial ve Times Roman yazı tiplerini Aspose.Words for .NET ile meta dosyası boyutuna atlamak için özelliğin nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgede yazı tipi gömme modu seçeneğini nasıl yapılandıracağınızı ve Arial ve Times Roman yazı tiplerini gömmeden bir PDF oluşturmayı öğrenebileceksiniz.

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

## 3. Adım: Yazı tipi gömme ile PDF olarak kaydetme seçeneklerini yapılandırın

 Oluşturulan PDF'ye Arial ve Times Roman yazı tiplerini yerleştirmeyi atlamak için,`PdfSaveOptions` nesne ve ayarlayın`FontEmbeddingMode` mülkiyet`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## 4. Adım: Belgeyi katıştırılmış yazı tipleri olmadan PDF olarak kaydedin

Son olarak, daha önce yapılandırılmış kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Bu kadar ! Aspose.Words for .NET kullanarak Arial ve Times Roman yazı tiplerini gömmeden başarıyla bir PDF oluşturdunuz.

### Aspose.Words for .NET ile gömülü Arial ve Times Roman yazı tiplerini meta dosyası boyutunda atlamak için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```
