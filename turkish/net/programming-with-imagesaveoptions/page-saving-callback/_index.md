---
title: Sayfa Tasarruflu Geri Arama
linktitle: Sayfa Tasarruflu Geri Arama
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile belge sayfalarını görüntülere kaydetmeyi nasıl özelleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-imagesaveoptions/page-saving-callback/
---

Bu öğreticide, .NET için Aspose.Words görüntü kaydetme seçenekleriyle sayfa kaydetme geri aramasını kullanmak için sağlanan C# kaynak kodunu keşfedeceğiz. Bu özellik, bir belgenin her sayfasını görüntü olarak kaydederken özel eylemler gerçekleştirmenizi sağlar.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 Bu adımda, yeni bir görüntü oluşturarak görüntü kaydetme seçeneklerini yapılandırıyoruz.`ImageSaveOptions` nesne. İstenilen yedekleme formatını burada PNG formatı için "Png" olarak belirtiyoruz. Kullanırız`PageSet` burada belgenin ilk sayfasından son sayfasına kadar kaydedilecek sayfa aralığını belirtmek için (`doc.PageCount - 1`). biz de ayarladık`PageSavingCallback` örneğine`HandlePageSavingCallback`, sayfa kaydetme geri aramasını işlemek için özel bir sınıftır.

## 4. Adım: Sayfayı Kaydet Geri Aramasını Uygulama

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

 Bu adımda, uyguladığımız`HandlePageSavingCallback` uygulayan sınıf`IPageSavingCallback` arayüz. Özel eylemlerinizi ekleyerek bu sınıfı özelleştirebilirsiniz.`PageSaving` yöntem. Sayfa bilgilerine şu adresten ulaşabilirsiniz:`args.PageIndex`mülkiyeti`PageSavingArgs` argüman olarak iletilen nesne.

## 5. Adım: Sayfaları resim olarak kaydetme

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 Bu son adımda, belgenin her sayfasını kullanarak bir görüntü olarak kaydediyoruz.`Save` yöntemi ve yolu çıkış dosyasına iletmek`.png` uzantı, belirtilen kaydetme seçenekleriyle birlikte.

Artık belgenin her sayfasını bir görüntü olarak kaydederken özel eylemler gerçekleştirmek için kaynak kodunu çalıştırabilirsiniz. Ortaya çıkan dosya, "WorkingWithImageSaveOptions.PageSavingCallback.png" adıyla belirtilen dizine kaydedilecektir.

### Aspose.Words for .NET kullanan Sayfa Kaydetme Geri Çağırması için örnek kaynak kodu


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

Bu öğreticide, .NET için Aspose.Words görüntü kaydetme seçenekleriyle sayfa kaydetme geri çağırma işlevini inceledik. Bir belgenin her sayfasını resim olarak kaydederken özel eylemlerin nasıl gerçekleştirileceğini öğrendik.

Bu özellik, görüntülere dönüştürürken her sayfada belirli işlemler yapmak istediğinizde kullanışlıdır. Sayfa bilgilerine erişebilir ve bunu yedekleme seçeneklerini özelleştirmek veya sayfaya özgü diğer işlemleri gerçekleştirmek için kullanabilirsiniz.

Aspose.Words for .NET, belge işleme ve oluşturma için çok çeşitli gelişmiş özellikler sunar. Sayfayı Kaydet Hatırlatıcı, sayfaları resimlere kaydetme sürecini özelleştirmeniz için size sunduğu birçok güçlü araçtan biridir.