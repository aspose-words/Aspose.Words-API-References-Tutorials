---
title: Jpeg Sayfa Aralığını Alın
linktitle: Jpeg Sayfa Aralığını Alın
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile çeşitli JPEG sayfalarını nasıl elde edeceğinizi öğrenin. Özel görüntüleri ayıklamak için eksiksiz eğitim.
type: docs
weight: 10
url: /tr/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

Bu öğreticide, Aspose.Words for .NET ile "Get Range of JPEG Pages" özelliği için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, bir belgenin belirli bir sayfa aralığını JPEG biçimindeki görüntülere dönüştürmenize olanak tanır.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, geliştirme ortamınızı Aspose.Words for .NET ile kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## 2. Adım: Belgeyi yükleme

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Bu adımda, kullanarak belgeyi yüklüyoruz`Document` yöntemi ve yolu yüklenecek DOCX dosyasına geçirme.

## 3. Adım: Görüntü yedekleme seçeneklerini yapılandırın

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 Bu adımda, görüntüler için yedekleme seçeneklerini yapılandırıyoruz. yeni bir tane yaratıyoruz`ImageSaveOptions` istenen kaydetme biçimini belirten nesne, burada JPEG biçimi için "Jpeg". Ayrıca, dönüştürülecek sayfa aralığını da ayarladık.`PageSet`nesne. Son olarak, kullanarak görüntünün parlaklığını ve kontrastını ayarlıyoruz.`ImageBrightness` Ve`ImageContrast` sırasıyla özellikler. Ayrıca kullanarak yatay çözünürlüğü de değiştiriyoruz.`HorizontalResolution` mülk.

## 4. Adım: Görüntüleri yedekleme

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 Bu son adımda, belirtilen sayfa aralığının görüntülerini JPEG formatında kaydediyoruz.`Save` yöntemi ve yolu, belirtilen kaydetme seçenekleriyle birlikte çıktı dosyasına geçirme.

Artık belgenizdeki belirli bir sayfa aralığını JPEG görüntülere dönüştürmek için kaynak kodunu çalıştırabilirsiniz. Ortaya çıkan dosya, "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg" adıyla belirtilen dizine kaydedilecektir.

### Aspose.Words For .NET kullanarak Get Jpeg Page Range için örnek kaynak kodu

```csharp 
 //Belge dizininizin yolu
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Belgenin yalnızca ilk sayfasını dönüştürmek için "PageSet" değerini "0" olarak ayarlayın.
options.PageSet = new PageSet(0);

// Görüntünün parlaklığını ve kontrastını değiştirin.
// Her ikisi de 0-1 ölçeğindedir ve varsayılan olarak 0,5'tir.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Yatay çözünürlüğü değiştirin.
// Bu özellikler için varsayılan değer, 96dpi çözünürlük için 96.0'dır.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET ile bir JPEG sayfa aralığı almanın işlevselliğini inceledik. Kaydetme seçeneklerini özelleştirirken, bir belgenin belirli bir sayfa aralığını JPEG biçimindeki görüntülere nasıl dönüştüreceğimizi öğrendik.

Bu özellik, bir belgeden belirli sayfaları çıkarmak ve bunları JPEG görüntüleri olarak kaydetmek istediğinizde kullanışlıdır. Kişiselleştirilmiş sonuçlar elde etmek için görüntülerin parlaklığını, kontrastını ve yatay çözünürlüğünü de ayarlayabilirsiniz.

Aspose.Words for .NET, belge işleme ve oluşturma için çok çeşitli gelişmiş özellikler sunar. Bir JPEG sayfa aralığı elde etmek, kullanımınıza sunduğu birçok güçlü araçtan biridir.

Belgelerinizden yüksek kaliteli JPEG görüntüleri elde etmek için bu özelliği Aspose.Words for .NET projelerinize entegre etmekten çekinmeyin.