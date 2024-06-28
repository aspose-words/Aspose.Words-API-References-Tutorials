---
title: Wmf Yazı Tiplerini Meta Dosya Boyutuna Ölçeklendirerek PDF Boyutunu Azaltın
linktitle: Wmf Yazı Tiplerini Meta Dosya Boyutuna Ölçeklendirerek PDF Boyutunu Azaltın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile PDF'ye dönüştürürken wmf yazı tiplerini meta dosya boyutuna ölçeklendirerek pdf boyutunu küçültmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Bu makale, Aspose.Words for .NET ile wmf yazı tiplerini meta dosya boyutuna ölçeklendirme özelliğiyle pdf boyutunun nasıl azaltılacağı konusunda adım adım bir kılavuz sağlar. Kodun her bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, PDF'ye dönüştürürken WMF yazı tipi ölçeklendirmenin nasıl etkinleştirileceğini veya devre dışı bırakılacağını anlayabileceksiniz.

Başlamadan önce projenize Aspose.Words for .NET kütüphanesini kurup yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için belgelerinizin bulunduğu dizinin yolunu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` Belgeler dizininizin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Daha sonra işlemek istediğimiz belgeyi yüklememiz gerekiyor. Bu örnekte, belgenin "text.docx içeren WMF" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## 3. Adım: Meta dosyası oluşturma seçeneklerini yapılandırma

 WMF yazı tipi ölçeklendirmesini meta dosya boyutuna göre etkinleştirmek veya devre dışı bırakmak için,`MetafileRenderingOptions` nesne. Bu örnekte, yazı tipi ölçeklendirmeyi ayarlayarak devre dışı bırakıyoruz.`ScaleWmfFontsToMetafileSize`mülkiyet`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## 4. Adım: PDF olarak kaydetme seçeneklerini meta dosya oluşturma seçenekleriyle yapılandırın

Son olarak, daha önce yapılandırılan meta dosya oluşturma seçeneklerini kullanarak PDF'ye kaydetme seçeneklerini yapılandırabiliriz.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Adım 5: Meta Dosyası Oluşturma Seçenekleri ile Belgeyi PDF Olarak Kaydetme

Daha önce yapılandırılan kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Bu kadar ! Dönüştürme sırasında WMF yazı tipi ölçeklendirmesini meta dosya boyutuna başarıyla etkinleştirdiniz veya devre dışı bıraktınız

Aspose.Words for .NET kullanan bir PDF belgesi.

### Aspose.Words for .NET ile WMF yazı tiplerini meta dosya boyutuna ölçeklendirmek için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	//Aspose.Words bazı meta dosyası kayıtlarını vektör grafiklerine doğru şekilde işleyemiyorsa
	// daha sonra Aspose.Words bu meta dosyasını bir bitmap'e dönüştürür.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak bir PDF belgesinde WMF yazı tiplerinin meta dosya boyutuna göre yeniden boyutlandırılmasının nasıl etkinleştirilip devre dışı bırakılacağını açıkladık. Açıklanan adımları izleyerek, bir PDF belgesine dönüştürürken WMF yazı tiplerinin meta dosya boyutuyla eşleşecek şekilde yeniden boyutlandırılması gerekip gerekmediğini kolayca kontrol edebilirsiniz. Bu, oluşturulan PDF dosyasının boyutunu azaltmanıza ve oluşturma performansını artırmanıza yardımcı olabilir. Belgelerinizin doğru yolunu belirttiğinizden ve meta dosyası oluşturma seçeneklerini gerektiği gibi yapılandırdığınızdan emin olun.

### Sıkça Sorulan Sorular

#### S: Bir PDF belgesinde WMF yazı tiplerini meta dosya boyutuna göre yeniden boyutlandırmak nedir?
C: PDF belgesindeki WMF yazı tiplerini meta dosya boyutuna göre yeniden boyutlandırmak, WMF yazı tiplerinin PDF belgesine dönüştürürken meta dosya boyutuyla eşleşecek şekilde ölçeklendirilmesi gerekip gerekmediğini kontrol eden bir özelliktir. Bu özellik etkinleştirildiğinde, WMF yazı tipleri meta dosyanın boyutuna uyacak şekilde ölçeklendirilir; bu, oluşturulan PDF belgesinin boyutunu küçültebilir.

#### S: Bir PDF belgesinde WMF yazı tiplerinin meta dosya boyutuna göre yeniden boyutlandırılmasını etkinleştirmek veya devre dışı bırakmak için Aspose.Words for .NET'i nasıl kullanabilirim?
C: Aspose.Words for .NET kullanarak bir PDF belgesinde WMF yazı tiplerinin meta dosya boyutuna göre yeniden boyutlandırılmasını etkinleştirmek veya devre dışı bırakmak için şu adımları izleyin:

 Belgelerinizin bulunduğu dizin yolunu değiştirerek ayarlayın.`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

 İşlemek istediğiniz belgeyi kullanarak yükleyin.`Document` sınıfını seçin ve belirtilen belgeler dizinindeki Word belgesinin yolunu belirtin.

 Bir örneğini oluşturarak meta dosyası oluşturma seçeneklerini yapılandırın.`MetafileRenderingOptions` sınıf ve ayarlama`ScaleWmfFontsToMetafileSize`mülkiyet`true` WMF yazı tiplerinin meta dosya boyutuna ölçeklenmesini etkinleştirmek veya`false` Bu özelliği devre dışı bırakmak için.

 Bir örneğini oluşturarak PDF olarak kaydetme seçeneklerini yapılandırın.`PdfSaveOptions` sınıfını kullanarak ve daha önce yapılandırılan meta dosyası oluşturma seçeneklerini kullanarak.

 Belgeyi kullanarak PDF formatında kaydedin.`Save` yöntemi`Document` yolu ve kaydetme seçeneklerini belirten sınıf.

#### S: Bir PDF belgesinde WMF yazı tiplerini meta dosya boyutuna göre yeniden boyutlandırmanın faydaları nelerdir?
C: Bir PDF belgesinde WMF yazı tiplerini meta dosya boyutuna göre yeniden boyutlandırmanın avantajları şunlardır:

PDF dosya boyutunu küçültme: WMF yazı tiplerini meta dosya boyutuna göre yeniden boyutlandırmak, yazı tipi boyutunu meta dosya ihtiyaçlarına göre uyarlayarak oluşturulan PDF belgesinin boyutunu azaltabilir.

Geliştirilmiş performans: WMF yazı tiplerinin boyutunu meta dosyanın boyutlarına göre ayarlayarak PDF belgesinin oluşturulması daha hızlı ve daha verimli olabilir.