---
title: Jpeg Sayfa Aralığını Al
linktitle: Jpeg Sayfa Aralığını Al
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile çeşitli JPEG sayfalarını nasıl elde edeceğinizi öğrenin. Özel görüntülerin çıkarılmasına yönelik eksiksiz eğitim.
type: docs
weight: 10
url: /tr/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

Bu eğitimde Aspose.Words for .NET ile "JPEG Sayfa Aralığını Al" özelliği için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, bir belgenin belirli bir sayfa aralığını JPEG formatındaki görüntülere dönüştürmenize olanak tanır.

## 1. Adım: Ortamı ayarlama

Başlamadan önce Aspose.Words for .NET ile geliştirme ortamınızı kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## Adım 2: Belgeyi yükleme

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Bu adımda belgeyi aşağıdaki komutu kullanarak yüklüyoruz:`Document` yöntemi ve yüklenecek DOCX dosyasının yolunu iletme.

## 3. Adım: Görüntü yedekleme seçeneklerini yapılandırın

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 Bu adımda imajlar için yedekleme seçeneklerini yapılandırıyoruz. Yeni bir tane yaratıyoruz`ImageSaveOptions` İstenilen kaydetme biçimini belirten nesne, burada JPEG biçimi için "Jpeg" bulunur. Ayrıca, dönüştürülecek sayfa aralığını da kullanarak ayarlıyoruz.`PageSet`nesne. Son olarak görüntünün parlaklığını ve kontrastını kullanarak ayarlıyoruz.`ImageBrightness`Ve`ImageContrast` sırasıyla özellikler. Ayrıca yatay çözünürlüğü de değiştiriyoruz.`HorizontalResolution` mülk.

## 4. Adım: Görüntüleri yedekleme

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 Bu son adımda belirtilen sayfa aralığındaki görselleri JPEG formatında kaydediyoruz.`Save` yöntemini kullanarak ve belirtilen kaydetme seçenekleriyle birlikte çıktı dosyasına giden yolu iletebilirsiniz.

Artık belgenizdeki belirli bir sayfa aralığını JPEG görüntülerine dönüştürmek için kaynak kodunu çalıştırabilirsiniz. Ortaya çıkan dosya, "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg" adıyla belirtilen dizine kaydedilecektir.

### Aspose.Words For .NET kullanarak Jpeg Sayfa Aralığı Alma için örnek kaynak kodu

```csharp 
 // Belge dizininizin yolu
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Bir belgenin yalnızca ilk sayfasını dönüştürmek için "PageSet"i "0" olarak ayarlayın.
options.PageSet = new PageSet(0);

// Görüntünün parlaklığını ve kontrastını değiştirin.
// Her ikisi de 0-1 ölçeğindedir ve varsayılan olarak 0,5'tir.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Yatay çözünürlüğü değiştirin.
// Bu özelliklerin varsayılan değeri 96 dpi çözünürlük için 96,0'dır.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Çözüm

Bu eğitimde Aspose.Words for .NET ile JPEG sayfa aralığı elde etmenin işlevselliğini araştırdık. Kaydetme seçeneklerini özelleştirirken, bir belgenin belirli bir sayfa aralığını JPEG formatındaki görüntülere nasıl dönüştüreceğimizi öğrendik.

Bu özellik, bir belgeden belirli sayfaları çıkarmak ve bunları JPEG görüntüleri olarak kaydetmek istediğinizde kullanışlıdır. Kişiselleştirilmiş sonuçlar elde etmek için görüntülerin parlaklığını, kontrastını ve yatay çözünürlüğünü de ayarlayabilirsiniz.

Aspose.Words for .NET, belge işleme ve oluşturma için çok çeşitli gelişmiş özellikler sunar. JPEG sayfa aralığı elde etmek, kullanımınıza sunduğu birçok güçlü araçtan biridir.

Belgelerinizden yüksek kalitede JPEG görüntüler elde etmek için bu özelliği Aspose.Words for .NET projelerinize entegre etmekten çekinmeyin.