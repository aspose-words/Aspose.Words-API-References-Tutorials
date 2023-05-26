---
title: Anahat Seçeneklerini Ayarla
linktitle: Anahat Seçeneklerini Ayarla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir PDF belgesinde anahat seçeneklerini ayarlamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/set-outline-options/
---

Bu makale, Aspose.Words for .NET ile anahat seçeneklerini meta dosyası boyutuna ayarla özelliğinin nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgede anahat seçeneklerini nasıl ayarlayacağınızı ve karşılık gelen anahat seçenekleriyle bir PDF oluşturmayı öğrenebileceksiniz.

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

## 3. Adım: Plan seçenekleriyle PDF olarak kaydetme seçeneklerini yapılandırın

 Oluşturulan PDF'de anahat seçeneklerini ayarlamak için,`PdfSaveOptions` nesne. Başlık anahat düzeylerinin sayısını ayarlayabiliriz (`HeadingsOutlineLevels`) ve genişletilmiş anahat düzeylerinin sayısı (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## 4. Adım: Anahat seçenekleriyle belgeyi PDF olarak kaydedin

Son olarak, daha önce yapılandırılmış kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

Bu kadar ! Aspose.Words for .NET'i kullanarak bir belgede anahat seçeneklerini başarıyla belirlediniz ve karşılık gelen anahat seçenekleriyle bir PDF oluşturdunuz.

### Aspose.Words for .NET ile plan seçeneklerini meta dosyası boyutuna ayarlamak için örnek kaynak kodu


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```
