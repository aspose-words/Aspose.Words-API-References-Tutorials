---
title: PDF Belgesinde Görüntü Sıkıştırma
linktitle: PDF Belgesinde Görüntü Sıkıştırma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile PDF Belgesindeki görüntüleri sıkıştırmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/image-compression/
---

Bu makale, Aspose.Words for .NET ile PDF Belgesinde Görüntü Sıkıştırma özelliğinin nasıl kullanılacağına ilişkin adım adım bir kılavuz sağlar. Kodun her bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgedeki görüntülerin nasıl sıkıştırılacağını ve uygun görüntü sıkıştırmasıyla bir PDF'nin nasıl oluşturulacağını anlayabileceksiniz.

Başlamadan önce projenize Aspose.Words for .NET kütüphanesini kurup yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için belgelerinizin bulunduğu dizinin yolunu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` Belgeler dizininizin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Daha sonra işlemek istediğimiz belgeyi yüklememiz gerekiyor. Bu örnekte belgenin "Rendering.docx" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: Görüntü sıkıştırmayla PDF olarak kaydetme seçeneklerini yapılandırın

 PDF'ye dönüştürürken görüntüleri sıkıştırmak için`PdfSaveOptions` nesne. Gerekirse görüntü sıkıştırma türünü, JPEG kalitesini ve diğer PDF uyumluluk seçeneklerini ayarlayabiliriz.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## 4. Adım: Belgeyi görüntü sıkıştırmayla PDF olarak kaydedin

Son olarak daha önce yapılandırdığımız kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## 5. Adım: Görüntü sıkıştırmayla PDF/A-2u'ya kaydetme seçeneklerini yapılandırın

Görüntü sıkıştırmayla PDF/A-2u uyumlu PDF oluşturmak istiyorsanız ek kaydetme seçeneklerini yapılandırabilirsiniz.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Dosya boyutunu küçültmek için %50 kalitede JPEG sıkıştırmasını kullanın.
};
```

## Adım 6: Belgeyi görüntü sıkıştırmayla PDF/A-2u olarak kaydedin

Daha önce yapılandırılan ek kaydetme seçeneklerini kullanarak belgeyi PDF/A-2u formatında kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



Bu kadar ! Aspose.Words for .NET'i kullanarak bir belgedeki görüntüleri başarıyla sıkıştırdınız ve uygun görüntü sıkıştırmasıyla bir PDF oluşturdunuz.

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
		JpegQuality = 100, // Dosya boyutunu azaltmak için %50 kalitede JPEG sıkıştırmasını kullanın.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir PDF belgesindeki görüntülerin nasıl sıkıştırılacağını açıkladık. Açıklanan adımları takip ederek PDF belgenizdeki görsellerin boyutunu kolaylıkla küçültebilir ve uygun görsel sıkıştırmaya sahip bir PDF oluşturabilirsiniz. Görüntü kalitesini korurken PDF belgelerinizin boyutunu optimize etmek için Aspose.Words for .NET'in görüntü sıkıştırma özelliklerini kullanın.

### Sıkça Sorulan Sorular

#### S: PDF belgesinde görüntü sıkıştırma nedir?
C: Bir PDF belgesindeki görüntülerin sıkıştırılması, PDF dosyasının genel boyutunu azaltmak için PDF belgesinde yer alan görüntülerin boyutunu küçültmektir. Bu, gereken depolama alanını azaltır ve PDF'yi yüklerken ve görüntülerken performansı artırır.

#### S: Aspose.Words for .NET ile bir PDF belgesindeki görüntüleri nasıl sıkıştırabilirim?
C: Bir PDF belgesindeki görüntüleri Aspose.Words for .NET ile sıkıştırmak için şu adımları izleyin:

 Bir örneğini oluşturun`Document` Word belgesinin yolunu belirten sınıf.

 Bir örneğini oluşturun`PdfSaveOptions` sınıfı seçin ve ayarlayın`ImageCompression`mülkiyet`PdfImageCompression.Jpeg` JPEG sıkıştırmasını kullanmak için.

İhtiyaçlarınıza göre JPEG kalitesi gibi diğer görüntü sıkıştırma seçeneklerini de ayarlayabilirsiniz.

 Kullan`Save` yöntemi`Document`Kaydetme seçeneklerini belirterek belgeyi PDF formatında kaydetmek için sınıf.

#### S: Standart görüntü sıkıştırma ile PDF/A-2u görüntü sıkıştırma arasındaki fark nedir?
C: Standart görüntü sıkıştırma, form alanlarını korurken PDF belgesindeki görüntülerin boyutunu azaltır. Bu, form alanı işlevselliğinden ödün vermeden PDF dosyasının genel boyutunu azaltır.

PDF/A-2u ile Görüntü Sıkıştırma, görüntü sıkıştırma uygularken PDF/A-2u standardına uygun bir PDF dosyası oluşturmanıza olanak tanıyan ek bir seçenektir. PDF/A-2u, arşivlenen PDF belgeleri için bir ISO standardıdır ve belgelerin uzun süreli korunmasını garanti eder.
