---
title: Görüntüleri Alt Örnekleme
linktitle: Görüntüleri Alt Örnekleme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile PDF'ye dönüştürürken görüntü çözünürlüğünü nasıl azaltacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/downsampling-images/
---

Bu eğitimde, Aspose.Words for .NET ile PDF'ye dönüştürürken görüntü çözünürlüğünü düşürme adımlarında size yol göstereceğiz. Bu, oluşturulan PDF dosyasının boyutunu azaltır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme

PDF'ye dönüştürmek istediğiniz belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Belgenize giden doğru yolu belirttiğinizden emin olun.

## 2. Adım: PDF kaydetme seçeneklerini yapılandırın

PdfSaveOptions sınıfının bir örneğini oluşturun ve görüntü küçültme seçeneklerini ayarlayın:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 bu`Resolution` özelliği, görüntülerin hedef çözünürlüğünü belirtir ve`ResolutionThreshold` özelliği, altındaki görüntülerin küçültülmeyeceği minimum çözünürlüğü belirtir.

## 3. Adım: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` kaydetme seçeneklerini belirterek belgeyi PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Görüntüleri Alt Örnekleme için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//Aşağı örnekleme için minimum bir eşik belirleyebiliriz.
	// Bu değer, girdi belgesindeki ikinci görüntünün altörneklenmesini önleyecektir.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Bu adımları izleyerek, Aspose.Words for .NET ile PDF'ye dönüştürürken görüntü çözünürlüğünü kolayca azaltabilirsiniz.


