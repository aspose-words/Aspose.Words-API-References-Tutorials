---
title: Tiff Sayfa Aralığını Alın
linktitle: Tiff Sayfa Aralığını Alın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile çeşitli TIFF sayfalarını nasıl çıkaracağınızı öğrenin. Özel TIFF dosyaları için eğitimi tamamlayın.
type: docs
weight: 10
url: /tr/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

Bu eğitimde, Aspose.Words for .NET ile çeşitli TIFF sayfaları elde etmek için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, bir belgeden belirli bir aralıktaki sayfaları çıkarmanıza ve bunları TIFF dosyası olarak kaydetmenize olanak tanır.

## 1. Adım: Ortamı ayarlama

Başlamadan önce Aspose.Words for .NET ile geliştirme ortamınızı kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## Adım 2: Belgeyi yükleme

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Bu adımda belgeyi aşağıdaki komutu kullanarak yüklüyoruz:`Document` yöntemi ve yüklenecek DOCX dosyasının yolunu iletme.

## 3. Adım: Belgenin tamamını TIFF'e kaydetme

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

 Bu adımda belgenin tamamını TIFF formatında kaydediyoruz.`Save` yöntemi ve uzantılı çıktı dosyasının yolunu belirtme`.tiff`.

## 4. Adım: Sayfa aralığı için yedekleme seçeneklerini yapılandırın

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 Bu adımda belirli sayfa aralığı için yedekleme seçeneklerini yapılandırıyoruz. Yeni bir tane yaratıyoruz`ImageSaveOptions` İstenilen kaydetme formatını belirten nesne, burada TIFF formatı için "Tiff" bulunur. Kullanırız`PageSet` çıkarmak istediğimiz sayfa aralığını belirtmek için, burada sayfa 0'dan sayfa 1'e (dahil) kadar. Ayrıca TIFF sıkıştırmasını da şu şekilde ayarladık:`Ccitt4` ve çözünürlük 160 dpi'ye kadar.

## 5. Adım: Sayfa aralığını TIFF'e kaydetme

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 Bu son adımda belirtilen sayfa aralığını TIFF formatında kaydediyoruz.`Save`yöntemi ve çıktı dosyasına giden yolu iletmek`.tiff` uzantı, belirtilen kaydetme seçenekleriyle birlikte .

Artık belgenizden belirli bir sayfa aralığını almak ve bunları TIFF dosyası olarak kaydetmek için kaynak kodunu çalıştırabilirsiniz. Ortaya çıkan dosyalar, belgenin tamamı için "WorkingWithImageSaveOptions.MultipageTiff.tiff" ve belirtilen sayfa aralığı için "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" adlarıyla belirtilen dizine kaydedilecektir.

### Aspose.Words for .NET kullanarak Get Tiff Page Range'in örnek kaynak kodu

```csharp 

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## Çözüm

Bu eğitimde Aspose.Words for .NET ile çeşitli TIFF sayfaları almanın işlevselliğini araştırdık. Bir belgeden belirli bir aralıktaki sayfaları nasıl çıkaracağımızı ve bunları TIFF dosyası olarak nasıl kaydedeceğimizi öğrendik.

Bu özellik, bir belgeden yalnızca belirli sayfaları çıkarmak ve bunları TIFF gibi standart bir görüntü formatında kaydetmek istediğinizde kullanışlıdır. En iyi kalitede TIFF dosyalarını elde etmek için sıkıştırma ve çözünürlük seçeneklerini de özelleştirebilirsiniz.

Aspose.Words for .NET, belge işleme ve oluşturma için çok çeşitli gelişmiş özellikler sunar. TIFF sayfa aralığını edinmek, kullanımınıza sunduğu birçok güçlü araçtan biridir.

Belgelerinizden belirli sayfa aralıklarını TIFF formatında çıkarmak ve kaydetmek için bu işlevselliği Aspose.Words for .NET projelerinize entegre etmekten çekinmeyin.