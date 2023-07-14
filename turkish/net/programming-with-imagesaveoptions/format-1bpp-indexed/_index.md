---
title: Biçim 1Bpp Dizine Alınmış
linktitle: Biçim 1Bpp Dizine Alınmış
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile indekslenen 1 bpp'lik görüntülerin nasıl formatlanacağını öğrenin. Düşük renk derinliğine sahip görüntüler için eksiksiz öğretici.
type: docs
weight: 10
url: /tr/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
Bu eğitimde, Aspose.Words for .NET ile "Format 1Bpp Indexed" işlevi için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, bir belgedeki görüntüleri piksel başına 1 bit (1 bpp) renk derinliği ve dizinlenmiş renk modu ile PNG biçiminde biçimlendirmenize olanak tanır.

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 Bu adımda, görüntüler için yedekleme seçeneklerini yapılandırıyoruz. yeni bir tane yaratıyoruz`ImageSaveOptions`istenen kaydetme biçimini belirten nesne, PNG biçimi için burada "Png". Ayrıca görüntüye dahil edilecek sayfayı, siyah beyaz renk modunu ve indekslenmiş 1 bpp piksel formatını da tanımlıyoruz.

## 4. Adım: Görüntüleri yedekleme

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 Bu son adımda, belge resimlerini kullanarak PNG formatında kaydediyoruz.`Save` yöntemi ve yolu, belirtilen kaydetme seçenekleriyle birlikte çıktı dosyasına geçirme.

Artık belge görüntülerini PNG biçiminde, 1 bpp'lik bir renk derinliğiyle dizine eklenmiş olarak biçimlendirmek için kaynak kodunu çalıştırabilirsiniz. Ortaya çıkan dosya, "WorkingWithImageSaveOptions.Format1BppIndexed.Png" adıyla belirtilen dizine kaydedilecektir.

### Aspose.Words for .NET kullanılarak İndekslenen Format 1Bpp için örnek kaynak kodu

```csharp 
 
			 //Belge dizininizin yolu
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

Bu eğitimde, Aspose.Words for .NET ile 1Bpp Dizinlenmiş biçim özelliğini inceledik. Bir belgedeki görüntüleri piksel başına 1 bit (1 bpp) renk derinliği ve dizinlenmiş renk modu ile PNG biçiminde nasıl biçimlendireceğimizi öğrendik.

Bu özellik, düşük renk derinliğine ve küçük dosya boyutuna sahip görüntüler elde etmek istediğinizde kullanışlıdır. 1Bpp İndekslenmiş format, bazı özel uygulamalar için faydalı olabilecek indekslenmiş bir renk paleti kullanılarak görüntülerin temsil edilmesini sağlar.

Aspose.Words for .NET, belge işleme ve oluşturma için çok çeşitli gelişmiş özellikler sunar. 1Bpp Dizinlenmiş format, kullanımınıza sunduğu birçok güçlü araçtan biridir.