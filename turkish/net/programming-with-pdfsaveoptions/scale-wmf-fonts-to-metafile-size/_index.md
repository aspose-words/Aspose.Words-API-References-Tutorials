---
title: Wmf Yazı Tiplerini Meta Dosya Boyutuna Ölçeklendirerek PDF Boyutunu Küçültün
linktitle: Wmf Yazı Tiplerini Meta Dosya Boyutuna Ölçeklendirerek PDF Boyutunu Küçültün
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile PDF'ye dönüştürürken wmf yazı tiplerini meta dosyası boyutuna ölçeklendirerek pdf boyutunu küçültmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Bu makale, Aspose.Words for .NET ile wmf yazı tiplerini meta dosyası boyutuna ölçeklendir özelliğiyle pdf boyutunun nasıl küçültüleceğine dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, PDF'ye dönüştürürken WMF yazı tipi ölçeklendirmeyi nasıl etkinleştireceğinizi veya devre dışı bırakacağınızı anlayabileceksiniz.

Başlamadan önce, projenizde Aspose.Words for .NET kitaplığını kurduğunuzdan ve yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için, belgelerinizin bulunduğu dizine giden yolu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler dizininize giden gerçek yolla.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Ardından, işlemek istediğimiz belgeyi yüklememiz gerekiyor. Bu örnekte, belgenin "text.docx ile WMF" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## 3. Adım: Meta dosyası oluşturma seçeneklerini yapılandırın

 WMF yazı tipini meta dosyası boyutuna ölçeklendirmeyi etkinleştirmek veya devre dışı bırakmak için,`MetafileRenderingOptions`nesne. Bu örnekte, ayarlayarak yazı tipi ölçeklemeyi devre dışı bırakıyoruz.`ScaleWmfFontsToMetafileSize` mülkiyet`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## 4. Adım: Meta dosyası oluşturma seçenekleriyle PDF olarak kaydetme seçeneklerini yapılandırın

Son olarak, daha önce yapılandırılan meta dosyası oluşturma seçeneklerini kullanarak PDF'ye kaydet seçeneklerini yapılandırabiliriz.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## 5. Adım: Belgeyi Meta Dosya Oluşturma Seçenekleriyle PDF Olarak Kaydedin

Önceden yapılandırılmış kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Bu kadar ! Dönüştürürken WMF yazı tipini meta dosyası boyutuna ölçeklendirmeyi başarıyla etkinleştirdiniz veya devre dışı bıraktınız

Aspose.Words for .NET kullanan bir PDF belgesi.

### Aspose.Words for .NET ile WMF yazı tiplerini meta dosyası boyutuna ölçeklendirmek için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// Aspose.Words bazı meta dosyası kayıtlarını vektör grafiklerine doğru şekilde işleyemezse
	// ardından Aspose.Words bu meta dosyasını bir bitmap'e dönüştürür.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir PDF belgesinde WMF yazı tiplerinin meta dosyası boyutuna yeniden boyutlandırılmasının nasıl etkinleştirileceğini veya devre dışı bırakılacağını açıkladık. Açıklanan adımları izleyerek, bir PDF belgesine dönüştürürken WMF yazı tiplerinin meta dosya boyutuyla eşleşecek şekilde yeniden boyutlandırılması gerekip gerekmediğini kolayca kontrol edebilirsiniz. Bu, oluşturulan PDF dosyasının boyutunu küçültmenize ve işleme performansını artırmanıza yardımcı olabilir. Belgelerinize giden doğru yolu belirttiğinizden ve meta dosyası oluşturma seçeneklerini gerektiği gibi yapılandırdığınızdan emin olun.

### Sıkça Sorulan Sorular

#### S: Bir PDF belgesinde WMF yazı tiplerini meta dosyası boyutuna yeniden boyutlandırma nedir?
Y: Bir PDF belgesinde WMF yazı tiplerini meta dosyası boyutuna göre yeniden boyutlandırmak, bir PDF belgesine dönüştürülürken WMF yazı tiplerinin meta dosya boyutuyla eşleşecek şekilde ölçeklenip ölçeklenmeyeceğini denetleyen bir özelliktir. Bu özellik etkinleştirildiğinde, WMF yazı tipleri, oluşturulan PDF belgesinin boyutunu küçültebilecek şekilde meta dosyasının boyutuyla eşleşecek şekilde ölçeklenir.

#### S: Aspose.Words for .NET'i bir PDF belgesinde WMF yazı tiplerini meta dosyası boyutuna yeniden boyutlandırmayı etkinleştirmek veya devre dışı bırakmak için nasıl kullanabilirim?
C: Aspose.Words for .NET kullanarak bir PDF belgesinde WMF yazı tiplerinin meta dosyası boyutuna yeniden boyutlandırılmasını etkinleştirmek veya devre dışı bırakmak için şu adımları izleyin:

 Değiştirerek belgelerinizin bulunduğu dizin yolunu ayarlayın.`"YOUR DOCUMENT DIRECTORY"` belgeler dizininizin gerçek yolu ile.

 kullanarak işlemek istediğiniz belgeyi yükleyin.`Document` sınıfı ve belirtilen belgeler dizinindeki Word belgesinin yolunu belirtin.

 örneğini oluşturarak meta dosyası oluşturma seçeneklerini yapılandırın.`MetafileRenderingOptions` sınıf ve ayar`ScaleWmfFontsToMetafileSize` mülkiyet`true` WMF yazı tiplerinin meta dosyası boyutuna ölçeklenmesini etkinleştirmek veya`false` Bu özelliği devre dışı bırakmak için.

 örneğini oluşturarak PDF olarak kaydetme seçeneklerini yapılandırın.`PdfSaveOptions` sınıf ve daha önce yapılandırılan meta dosyası işleme seçeneklerini kullanma.

 kullanarak belgeyi PDF formatında kaydedin.`Save` yöntemi`Document`yolu ve kaydetme seçeneklerini belirten sınıf.

#### S: Bir PDF belgesinde WMF yazı tiplerini meta dosya boyutuna göre yeniden boyutlandırmanın faydaları nelerdir?
Y: Bir PDF belgesinde WMF yazı tiplerini meta dosya boyutuna göre yeniden boyutlandırmanın avantajları şunlardır:

PDF dosyası boyutunu küçültme: WMF yazı tiplerini meta dosyası boyutuna göre yeniden boyutlandırmak, yazı tipi boyutunu meta dosyası gereksinimlerine uyarlayarak oluşturulan PDF belgesinin boyutunu azaltabilir.

Geliştirilmiş performans: WMF yazı tiplerinin boyutunu meta dosyasının boyutlarına göre ayarlayarak, PDF belgesinin işlenmesi daha hızlı ve daha verimli olabilir.