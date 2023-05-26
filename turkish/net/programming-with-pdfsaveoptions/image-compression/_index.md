---
title: Görüntü Sıkıştırma
linktitle: Görüntü Sıkıştırma
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile görüntüleri sıkıştırmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/image-compression/
---

Bu makale, görüntü sıkıştırma özelliğinin Aspose.Words for .NET ile nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgedeki görüntüleri nasıl sıkıştıracağınızı ve uygun görüntü sıkıştırma ile bir PDF oluşturmayı öğrenebileceksiniz.

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

## 3. Adım: Görüntü sıkıştırma ile PDF olarak kaydetme seçeneklerini yapılandırın

 PDF'ye dönüştürürken görüntüleri sıkıştırmak için,`PdfSaveOptions` nesne. Gerekirse görüntü sıkıştırma türü, JPEG kalitesi ve diğer PDF uyumluluk seçeneklerini ayarlayabiliriz.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## 4. Adım: Görüntü sıkıştırma ile belgeyi PDF olarak kaydedin

Son olarak, daha önce yapılandırılmış kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## 5. Adım: Görüntü sıkıştırma ile PDF/A-2u'ya kaydetme seçeneklerini yapılandırın

Görüntü sıkıştırmalı PDF/A-2u uyumlu PDF oluşturmak istiyorsanız, ek kaydetme seçeneklerini yapılandırabilirsiniz.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Dosya boyutunu azaltmak için %50 kalitede JPEG sıkıştırması kullanın.
};
```

## 6. Adım: Belgeyi görüntü sıkıştırmalı PDF/A-2u olarak kaydedin

Daha önce yapılandırılan ek kaydetme seçeneklerini kullanarak belgeyi PDF/A-2u formatında kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



Bu kadar ! Aspose.Words for .NET'i kullanarak bir belgedeki görüntüleri başarıyla sıkıştırdınız ve uygun görüntü sıkıştırmayla bir PDF oluşturdunuz.

### Aspose.Words for .NET ile görüntüleri sıkıştırmak için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Dosya boyutunu azaltmak için %50 kalitede JPEG sıkıştırması kullanın.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```
