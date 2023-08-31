---
title: Tiff Sayfa Aralığı Alın
linktitle: Tiff Sayfa Aralığı Alın
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir dizi TIFF sayfasını nasıl çıkaracağınızı öğrenin. Özel TIFF dosyaları için eksiksiz öğretici.
type: docs
weight: 10
url: /tr/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

Bu öğreticide, Aspose.Words for .NET ile bir dizi TIFF sayfası elde etmek için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, bir belgeden belirli bir sayfa aralığını ayıklamanıza ve bunları bir TIFF dosyası olarak kaydetmenize olanak tanır.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, geliştirme ortamınızı Aspose.Words for .NET ile kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## 2. Adım: Belgeyi yükleme

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Bu adımda, kullanarak belgeyi yüklüyoruz`Document` yöntemi ve yolu yüklenecek DOCX dosyasına geçirme.

## 3. Adım: Belgenin tamamını TIFF'e kaydetme

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

 Bu adımda, belgenin tamamını kullanarak TIFF formatında kaydediyoruz.`Save` yöntemi ve uzantılı çıktı dosyasının yolunu belirtme`.tiff`.

## 4. Adım: Sayfa aralığı için yedekleme seçeneklerini yapılandırın

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 Bu adımda, belirli sayfa aralığı için yedekleme seçeneklerini yapılandırıyoruz. yeni bir tane yaratıyoruz`ImageSaveOptions` istenen kaydetme biçimini belirten nesne, burada TIFF biçimi için "Tiff". Kullanırız`PageSet` ayıklamak istediğimiz sayfa aralığını burada 0. sayfadan 1. sayfaya (dahil) belirtmek için. Ayrıca TIFF sıkıştırmasını şu şekilde ayarladık:`Ccitt4` ve çözünürlük 160 dpi.

## 5. Adım: Sayfa aralığını TIFF'e kaydetme

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 Bu son adımda, belirtilen sayfa aralığını kullanarak TIFF formatında kaydediyoruz.`Save`yöntemi ve yolu çıktı dosyasına iletmek`.tiff` uzantı, belirtilen kaydetme seçenekleriyle birlikte .

Artık belgenizden belirli bir sayfa aralığı almak için kaynak kodunu çalıştırabilir ve bunları bir TIFF dosyası olarak kaydedebilirsiniz. Ortaya çıkan dosyalar, tam belge için "WorkingWithImageSaveOptions.MultipageTiff.tiff" ve belirtilen sayfa aralığı için "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" adlarıyla belirtilen dizine kaydedilecektir.

### Aspose.Words for .NET kullanan Get Tiff Page Range'in örnek kaynak kodu

```csharp 

//Belge dizininizin yolu
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

Bu öğreticide, Aspose.Words for .NET ile bir dizi TIFF sayfası almanın işlevselliğini inceledik. Bir belgeden belirli bir sayfa aralığını nasıl çıkaracağımızı ve bunları bir TIFF dosyası olarak nasıl kaydedeceğimizi öğrendik.

Bu özellik, bir belgeden yalnızca belirli sayfaları çıkarmak ve bunları TIFF gibi standart bir görüntü biçiminde kaydetmek istediğinizde kullanışlıdır. En iyi kalitede TIFF dosyalarını elde etmek için sıkıştırma ve çözünürlük seçeneklerini de özelleştirebilirsiniz.

Aspose.Words for .NET, belge işleme ve oluşturma için çok çeşitli gelişmiş özellikler sunar. TIFF sayfa aralığı almak, emrinize amade olduğu birçok güçlü araçtan biridir.

Belgelerinizden belirli sayfa aralıklarını ayıklamak ve TIFF formatında kaydetmek için bu işlevselliği Aspose.Words for .NET projelerinize entegre etmekten çekinmeyin.