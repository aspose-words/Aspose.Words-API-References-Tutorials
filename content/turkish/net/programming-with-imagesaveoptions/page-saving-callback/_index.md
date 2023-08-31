---
title: Sayfa Kaydederek Geri Arama
linktitle: Sayfa Kaydederek Geri Arama
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile belge sayfalarını görüntülere kaydetmeyi nasıl özelleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-imagesaveoptions/page-saving-callback/
---

Bu eğitimde, .NET için Aspose.Words görüntü kaydetme seçenekleriyle sayfa kaydetme geri çağırma işlevini kullanmak için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, bir belgenin her sayfasını resim olarak kaydederken özel eylemler gerçekleştirmenize olanak tanır.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 Bu adımda yeni bir dosya oluşturarak görsel kaydetme seçeneklerini yapılandırıyoruz.`ImageSaveOptions` nesne. İstediğiniz yedekleme formatını belirtiyoruz, burada PNG formatı için "Png" var. Kullanırız`PageSet` Kaydedilecek sayfa aralığını belirtmek için burada belgenin ilk sayfasından son sayfasına kadar (`doc.PageCount - 1`). Biz de belirledik`PageSavingCallback` bir örneğine`HandlePageSavingCallback`, sayfa kaydetme geri aramasını işlemek için özel bir sınıftır.

## Adım 4: Kaydetme Sayfasını Geri Aramayı Uygulama

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Özel eylemlerinizi burada uygulayın
         // Sayfa bilgilerine "args.PageIndex" özelliği aracılığıyla erişebilirsiniz.
         // Ayrıca her sayfa için kaydetme seçeneklerini ayrı ayrı değiştirebilirsiniz.
     }
}
```

 Bu adımda şunları uyguluyoruz:`HandlePageSavingCallback` uygulayan sınıf`IPageSavingCallback` arayüz. Özel eylemlerinizi ekleyerek bu sınıfı özelleştirebilirsiniz.`PageSaving` yöntem. sayfa bilgilerine şuradan ulaşabilirsiniz:`args.PageIndex` mülkiyeti`PageSavingArgs` nesne argüman olarak iletildi.

## 5. Adım: Sayfaları resim olarak kaydetme

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 Bu son adımda, belgenin her sayfasını kullanarak resim olarak kaydediyoruz.`Save` yöntemi ve çıktı dosyasına giden yolu iletmek`.png` uzantı, belirtilen kaydetme seçenekleriyle birlikte.

Artık belgenin her sayfasını görüntü olarak kaydederken özel eylemler gerçekleştirmek için kaynak kodunu çalıştırabilirsiniz. Ortaya çıkan dosya, "WorkingWithImageSaveOptions.PageSavingCallback.png" adıyla belirtilen dizine kaydedilecektir.

### Aspose.Words for .NET kullanarak Sayfa Kaydederek Geri Arama için örnek kaynak kodu


```csharp 
//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## Çözüm

Bu eğitimde, .NET için Aspose.Words görüntü kaydetme seçenekleriyle sayfa kaydetme geri çağırma işlevini araştırdık. Bir belgenin her sayfasını resim olarak kaydederken özel eylemlerin nasıl gerçekleştirileceğini öğrendik.

Bu özellik, görüntülere dönüştürürken her sayfada belirli işlemler gerçekleştirmek istediğinizde kullanışlıdır. Sayfa bilgilerine erişebilir ve bunu yedekleme seçeneklerini özelleştirmek veya sayfaya özel diğer işlemleri gerçekleştirmek için kullanabilirsiniz.

Aspose.Words for .NET, belge işleme ve oluşturma için çok çeşitli gelişmiş özellikler sunar. Sayfayı Kaydetme Hatırlatıcısı, sayfaları resimlere kaydetme işlemini özelleştirmenizi sağlayan birçok güçlü araçtan biridir.