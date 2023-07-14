---
title: PDF Belgesinde Görüntü Sıkıştırma
linktitle: PDF Belgesinde Görüntü Sıkıştırma
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir PDF Belgesinde görüntüleri sıkıştırmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/image-compression/
---

Bu makale, Aspose.Words for .NET ile bir PDF Belgesinde Görüntü Sıkıştırma özelliğinin nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgedeki görüntüleri nasıl sıkıştıracağınızı ve uygun görüntü sıkıştırma ile bir PDF oluşturmayı öğrenebileceksiniz.

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

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak bir PDF belgesindeki görüntülerin nasıl sıkıştırılacağını açıkladık. Açıklanan adımları izleyerek, PDF belgenizdeki görüntülerin boyutunu kolayca küçültebilir ve uygun görüntü sıkıştırmasıyla bir PDF oluşturabilirsiniz. Görüntü kalitesini korurken PDF belgelerinizin boyutunu optimize etmek için Aspose.Words for .NET'in görüntü sıkıştırma özelliklerini kullanın.

### Sıkça Sorulan Sorular

#### S: Bir PDF belgesinde görüntü sıkıştırma nedir?
Y: Bir PDF belgesindeki görüntüleri sıkıştırmak, PDF dosyasının genel boyutunu azaltmak için PDF belgesinde bulunan görüntülerin boyutunu küçültmek içindir. Bu, gereken depolama alanını azaltır ve PDF'yi yüklerken ve görüntülerken performansı artırır.

#### S: Bir PDF belgesindeki görüntüleri Aspose.Words for .NET ile nasıl sıkıştırabilirim?
C: Bir PDF belgesindeki görüntüleri Aspose.Words for .NET ile sıkıştırmak için şu adımları izleyin:

 örneğini oluşturun`Document` Word belgesine giden yolu belirten sınıf.

 örneğini oluşturun`PdfSaveOptions`sınıflandırın ve ayarlayın`ImageCompression` mülkiyet`PdfImageCompression.Jpeg` JPEG sıkıştırmasını kullanmak için.

JPEG kalitesi gibi diğer görüntü sıkıştırma seçeneklerini de ihtiyaçlarınıza göre ayarlayabilirsiniz.

 Kullan`Save` yöntemi`Document`kaydetme seçeneklerini belirterek belgeyi PDF biçiminde kaydetmek için sınıf.

#### S: Standart görüntü sıkıştırma ile PDF/A-2u görüntü sıkıştırma arasındaki fark nedir?
A: Standart görüntü sıkıştırma, form alanlarını korurken bir PDF belgesindeki görüntülerin boyutunu azaltır. Bu, form alanı işlevselliğinden ödün vermeden PDF dosyasının genel boyutunu azaltır.

PDF/A-2u ile Görüntü Sıkıştırma, görüntü sıkıştırma uygularken PDF/A-2u standardına uyan bir PDF dosyası oluşturmanıza olanak sağlayan ek bir seçenektir. PDF/A-2u, arşiv PDF belgeleri için bir ISO standardıdır ve belgelerin uzun süreli korunmasını garanti eder.
