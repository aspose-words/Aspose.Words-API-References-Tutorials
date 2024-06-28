---
title: Görüntüleri Alt Örnekleme ile PDF Belge Boyutunu Azaltın
linktitle: Görüntüleri Alt Örnekleme ile PDF Belge Boyutunu Azaltın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile PDF'ye dönüştürürken görüntüleri altörneklemeyle pdf belge boyutunu nasıl küçülteceğinizi öğrenin.
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

Belgenizin doğru yolunu belirttiğinizden emin olun.

## 2. Adım: PDF kaydetme seçeneklerini yapılandırın

PdfSaveOptions sınıfının bir örneğini oluşturun ve görüntünün boyutunu küçültme seçeneklerini ayarlayın:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

`Resolution` özelliği, görüntülerin hedef çözünürlüğünü ve`ResolutionThreshold`Özellik, görüntülerin küçültülmeyeceği minimum çözünürlüğü belirtir.

## 3. Adım: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` kaydetme seçeneklerini belirterek belgeyi PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Görüntüleri Alt Örneklemek için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Altörnekleme için minimum bir eşik ayarlayabiliriz.
	// Bu değer, giriş belgesindeki ikinci görüntünün altörneklenmesini önleyecektir.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Bu adımları izleyerek Aspose.Words for .NET ile PDF'ye dönüştürürken görüntü çözünürlüğünü kolayca azaltabilirsiniz.

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak PDF'ye dönüştürürken görüntü örneklemeyle bir PDF belgesinin boyutunun nasıl azaltılacağını açıkladık. Anlatılan adımları takip ederek görsellerin çözünürlüğünü ve oluşturulan PDF dosyasının boyutunu kolaylıkla azaltabilirsiniz. Belgenizin doğru yolunu belirttiğinizden ve görüntü örnekleme seçeneklerini gerektiği gibi yapılandırdığınızdan emin olun. PDF dosya boyutunun küçültülmesi, dosyanın farklı platformlarda paylaşılmasını, saklanmasını ve hızla yüklenmesini kolaylaştırır. Aspose.Words for .NET'i kullanarak görüntü örneklemeyle PDF belge boyutunu küçültmenin avantajlarından yararlanın.

### Sıkça Sorulan Sorular

#### S: Görüntü örneklemeyle PDF belgesinin boyutunu küçültmek nedir?
C: Görüntü Örnekleme ile PDF belge boyutunu küçültmek, PDF'ye dönüştürürken görüntülerin çözünürlüğünü azaltarak oluşturulan PDF dosyasının boyutunu azaltmaktır. Bu, depolama alanı kullanımını optimize eder ve PDF dosyasının paylaşılmasını ve aktarılmasını kolaylaştırır.

#### S: Aspose.Words for .NET'i kullanarak görüntü örneklemeyle PDF belge boyutunu nasıl küçültebilirim?
C: Aspose.Words for .NET kullanarak görüntü örneklemeyle PDF belge boyutunu küçültmek için şu adımları izleyin:

 Belgelerinizin bulunduğu dizin yolunu değiştirerek ayarlayın.`"YOUR DOCUMENTS DIRECTORY"` belge dizininizin gerçek yolu ile.

 PDF'ye dönüştürmek istediğiniz belgeyi kullanarak yükleyin.`Document` sınıfını seçin ve belirtilen belgeler dizinindeki belgenin yolunu belirtin.

 Bir örneğini oluşturarak PDF olarak kaydetme seçeneklerini yapılandırın.`PdfSaveOptions` kullanarak görüntü örnekleme seçeneklerini ayarlama ve sınıf oluşturma`DownsampleOptions` mülk. Görüntülerin hedef çözünürlüğünü kullanarak belirleyebilirsiniz.`Resolution` özelliğini kullanın ve görüntülerin ölçeğinin küçültülmeyeceği bir minimum çözünürlük eşiği ayarlayın.`ResolutionThreshold` mülk.

 Belgeyi kullanarak PDF formatında kaydedin.`Save` yöntemi`Document` yolu ve kaydetme seçeneklerini belirten sınıf.

#### S: Görüntü örneklemeyle PDF belge boyutunu küçültmenin faydaları nelerdir?
C: Görüntü örneklemeyle PDF belge boyutunu küçültmenin faydaları şunlardır:

Küçültülmüş PDF dosya boyutu: Görüntü örnekleme, PDF belgesindeki görüntülerin çözünürlüğünü azaltır, bu da PDF dosya boyutunun önemli ölçüde azalmasına neden olur. Bu, dosyayı özellikle e-posta yoluyla veya çevrimiçi olarak paylaşmayı ve aktarmayı kolaylaştırır.

Depolama alanının optimizasyonu: PDF dosyasının boyutunu azaltmak, özellikle yüksek çözünürlüklü görüntüler içeren çok sayıda PDF dosyanız olduğunda, depolama alanı kullanımını optimize etmenize yardımcı olur.

Performans iyileştirmeleri: Daha küçük PDF dosyaları daha hızlı yüklenir ve farklı cihazlarda daha hızlı açılıp görüntülenebilir.