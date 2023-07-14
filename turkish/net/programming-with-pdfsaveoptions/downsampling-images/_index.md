---
title: Görüntüleri Alt Örnekleme ile PDF Doküman Boyutunu Küçültün
linktitle: Görüntüleri Alt Örnekleme ile PDF Doküman Boyutunu Küçültün
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile PDF'ye dönüştürürken görüntüleri alt örnekleme ile pdf belge boyutunu nasıl küçülteceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/downsampling-images/
---

Bu eğitimde, Aspose.Words for .NET ile PDF'ye dönüştürürken görüntüleri altörnekleyerek pdf belge boyutunu küçültme adımlarında size yol göstereceğiz. Bu, oluşturulan PDF dosyasının boyutunu azaltır. Aşağıdaki adımları takip et:

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

 bu`Resolution` özelliği, görüntülerin hedef çözünürlüğünü belirtir ve`ResolutionThreshold`özelliği, altındaki görüntülerin küçültülmeyeceği minimum çözünürlüğü belirtir.

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

	// Aşağı örnekleme için minimum bir eşik belirleyebiliriz.
	// Bu değer, girdi belgesindeki ikinci görüntünün altörneklenmesini önleyecektir.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Bu adımları izleyerek, Aspose.Words for .NET ile PDF'ye dönüştürürken görüntü çözünürlüğünü kolayca azaltabilirsiniz.

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak PDF'ye dönüştürürken görüntü örneklemeyle bir PDF belgesinin boyutunun nasıl küçültüleceğini açıkladık. Açıklanan adımları izleyerek görüntülerin çözünürlüğünü ve oluşturulan PDF dosyasının boyutunu kolayca azaltabilirsiniz. Belgenize giden doğru yolu belirttiğinizden ve görüntü örnekleme seçeneklerini gerektiği gibi yapılandırdığınızdan emin olun. PDF dosya boyutunun küçültülmesi, dosyanın farklı platformlarda paylaşılmasını, saklanmasını ve hızla yüklenmesini kolaylaştırır. Aspose.Words for .NET kullanarak görüntü örnekleme ile PDF belge boyutunu küçültmenin avantajlarından yararlanın.

### Sıkça Sorulan Sorular

#### S: Görüntü örneklemeyle PDF belgesinin boyutunu küçülten nedir?
Y: Görüntü Örnekleme ile PDF belge boyutunu küçültmek, PDF'ye dönüştürürken görüntülerin çözünürlüğünü azaltarak oluşturulan PDF dosyasının boyutunu küçültmek içindir. Bu, depolama alanı kullanımını optimize eder ve PDF dosyasını paylaşmayı ve aktarmayı kolaylaştırır.

#### S: Aspose.Words for .NET kullanarak görüntü örneklemeyle PDF belge boyutunu nasıl küçültebilirim?
C: Aspose.Words for .NET kullanarak görüntü örneklemeyle PDF belge boyutunu küçültmek için şu adımları izleyin:

 Değiştirerek belgelerinizin bulunduğu dizin yolunu ayarlayın.`"YOUR DOCUMENTS DIRECTORY"` belgeler dizininizin gerçek yolu ile.

 kullanarak PDF'ye dönüştürmek istediğiniz belgeyi yükleyin.`Document` class ve belirtilen belgeler dizinindeki belgenin yolunu belirtin.

 örneğini oluşturarak PDF olarak kaydetme seçeneklerini yapılandırın.`PdfSaveOptions` kullanarak görüntü örnekleme seçeneklerini ayarlayın ve`DownsampleOptions` mülk. kullanarak görüntülerin hedef çözünürlüğünü belirleyebilirsiniz.`Resolution` özelliğini kullanarak görüntülerin ölçeğinin küçültülmeyeceği bir minimum çözünürlük eşiği ayarlayın.`ResolutionThreshold` mülk.

 kullanarak belgeyi PDF formatında kaydedin.`Save` yöntemi`Document`yolu ve kaydetme seçeneklerini belirten sınıf.

#### S: Görüntü örneklemeyle PDF belge boyutunu küçültmenin faydaları nelerdir?
C: Görüntü örneklemeyle PDF belge boyutunu küçültmenin faydaları şunlardır:

Küçültülmüş PDF dosya boyutu: Görüntü örnekleme, PDF belgesindeki görüntülerin çözünürlüğünü azaltarak PDF dosya boyutunda önemli bir azalmaya neden olur. Bu, özellikle e-posta veya çevrimiçi olarak dosyayı paylaşmayı ve aktarmayı kolaylaştırır.

Depolama alanının optimizasyonu: PDF dosyasının boyutunun küçültülmesi, özellikle yüksek çözünürlüklü görüntüler içeren çok sayıda PDF dosyanız olduğunda, depolama alanının kullanımını optimize etmeye yardımcı olur.

Performans iyileştirmeleri: Daha küçük PDF dosyaları daha hızlı yüklenir ve farklı cihazlarda daha hızlı açılıp görüntülenebilir.