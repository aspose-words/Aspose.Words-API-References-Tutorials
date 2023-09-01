---
title: 1Bpp Dizine Alınmış Biçim
linktitle: 1Bpp Dizine Alınmış Biçim
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile indekslenmiş görüntüleri 1 bpp'lik formatta nasıl formatlayacağınızı öğrenin. Düşük renk derinliğine sahip görüntüler için eğitimi tamamlayın.
type: docs
weight: 10
url: /tr/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
Bu eğitimde Aspose.Words for .NET ile "Format 1Bpp Indexed" işlevi için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, bir belgedeki görüntüleri piksel başına 1 bit (1 bpp) renk derinliği ve indekslenmiş renk modu ile PNG formatında formatlamanıza olanak tanır.

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 Bu adımda imajlar için yedekleme seçeneklerini yapılandırıyoruz. Yeni bir tane yaratıyoruz`ImageSaveOptions`İstenilen kaydetme biçimini belirten nesne, burada PNG biçimi için "Png" bulunur. Ayrıca görsele dahil edilecek sayfayı, siyah beyaz renk modunu ve indekslenmiş 1 bpp piksel formatını da tanımlıyoruz.

## 4. Adım: Görüntüleri yedekleme

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 Bu son adımda belge görsellerini PNG formatında kaydediyoruz.`Save` yöntemini kullanarak ve belirtilen kaydetme seçenekleriyle birlikte çıktı dosyasına giden yolu iletebilirsiniz.

Artık belge görüntülerini PNG formatında, indekslenmiş 1 bpp renk derinliğiyle biçimlendirmek için kaynak kodunu çalıştırabilirsiniz. Ortaya çıkan dosya, "WorkingWithImageSaveOptions.Format1BppIndexed.Png" adıyla belirtilen dizine kaydedilecektir.

### Aspose.Words for .NET kullanılarak İndekslenmiş Format 1Bpp için örnek kaynak kodu

```csharp 
 
			 // Belge dizininizin yolu
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Çözüm

Bu eğitimde Aspose.Words for .NET ile 1Bpp Indexed format özelliğini inceledik. PNG formatındaki bir belgedeki görüntüleri piksel başına 1 bit (1 bpp) renk derinliği ve indekslenmiş renk modu ile nasıl formatlayacağımızı öğrendik.

Bu özellik, düşük renk derinliğine ve küçük dosya boyutuna sahip görüntüler elde etmek istediğinizde kullanışlıdır. 1Bpp İndekslenmiş format, görüntülerin indekslenmiş bir renk paleti kullanılarak temsil edilmesine olanak tanır ve bu, bazı özel uygulamalar için yararlı olabilir.

Aspose.Words for .NET, belge işleme ve oluşturma için çok çeşitli gelişmiş özellikler sunar. 1Bpp İndekslenmiş format, kullanımınıza sunduğu birçok güçlü araçtan biridir.