---
title: Sayfa Kaydederek Geri Arama
linktitle: Sayfa Kaydederek Geri Arama
second_title: Aspose.Words Belge İşleme API'si
description: Ayrıntılı, adım adım kılavuzumuzla Aspose.Words for .NET'i kullanarak bir Word belgesinin her sayfasını ayrı bir PNG görüntüsü olarak kaydetmeyi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-imagesaveoptions/page-saving-callback/
---
## giriiş

Selam! Hiç bir Word belgesinin her sayfasını ayrı resimler olarak kaydetme ihtiyacını hissettiniz mi? Belki büyük bir raporu kolayca sindirilebilir görsellere bölmek istiyorsunuz ya da belki bir önizleme için küçük resimler oluşturmanız gerekiyor. Sebebiniz ne olursa olsun, Aspose.Words for .NET'i kullanmak bu görevi çok kolaylaştırıyor. Bu kılavuzda, bir belgenin her sayfasını ayrı bir PNG görüntüsü olarak kaydetmek için sayfa kaydetme geri araması ayarlama sürecinde size yol göstereceğiz. Haydi hemen dalalım!

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1.  Aspose.Words for .NET: Henüz yapmadıysanız adresinden indirip yükleyin.[Burada](https://releases.aspose.com/words/net/).
2. Visual Studio: Herhangi bir sürüm çalışmalıdır ancak bu kılavuz için Visual Studio 2019'u kullanacağım.
3. Temel C# Bilgisi: Devam etmek için temel bir C# anlayışına ihtiyacınız olacak.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktarmamız gerekiyor. Bu, her seferinde tam ad alanını yazmadan gerekli sınıflara ve yöntemlere erişmemize yardımcı olur.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1. Adım: Belge Dizininizi Kurun

Tamam, belge dizininizin yolunu tanımlayarak başlayalım. Burası giriş Word belgenizin bulunduğu ve çıktı resimlerinin kaydedileceği yerdir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgenizi Yükleyin

Daha sonra işlemek istediğiniz belgeyi yükleyeceğiz. Belgenizin ("Rendering.docx") belirtilen dizinde olduğundan emin olun.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: Görüntü Kaydetme Seçeneklerini Yapılandırın

Görüntüleri kaydetme seçeneklerini yapılandırmamız gerekiyor. Bu durumda sayfaları PNG dosyaları olarak kaydediyoruz.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

 Burada,`PageSet` Kaydedilecek sayfa aralığını belirtir ve`PageSavingCallback` özel geri arama sınıfımıza işaret eder.

## 4. Adım: Sayfa Kaydetme Geri Aramasını Uygulayın

Şimdi her sayfanın nasıl kaydedildiğini yöneten geri çağırma sınıfını uygulayalım.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

 Bu sınıf şunları uygular:`IPageSavingCallback` arayüzü ve bünyesinde`PageSaving` yöntemiyle, kaydedilen her sayfa için adlandırma modelini tanımlarız.

## Adım 5: Belgeyi Görüntü Olarak Kaydetme

Son olarak yapılandırılmış seçenekleri kullanarak belgeyi kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak bir Word belgesinin her sayfasını ayrı bir PNG görüntüsü olarak kaydetmek için sayfa kaydetme geri çağrısını başarıyla kurdunuz. Bu teknik, sayfa önizlemeleri oluşturmaktan, raporlar için ayrı sayfa görüntüleri oluşturmaya kadar çeşitli uygulamalar için inanılmaz derecede faydalıdır. 

Mutlu kodlama!

## SSS'ler

### Sayfaları PNG dışındaki formatlarda kaydedebilir miyim?  
 Evet, sayfaları değiştirerek JPEG, BMP ve TIFF gibi farklı formatlarda kaydedebilirsiniz.`SaveFormat` içinde`ImageSaveOptions`.

### Yalnızca belirli sayfaları kaydetmek istersem ne olur?  
 Kaydetmek istediğiniz sayfaları ayarlayarak belirleyebilirsiniz.`PageSet` parametre`ImageSaveOptions`.

### Görüntü kalitesini özelleştirmek mümkün mü?  
 Kesinlikle! Gibi özellikleri ayarlayabilirsiniz`ImageSaveOptions.JpegQuality` Çıktı görüntülerinin kalitesini kontrol etmek için.

### Büyük belgeleri verimli bir şekilde nasıl işleyebilirim?  
Büyük belgelerde, bellek kullanımını etkili bir şekilde yönetmek için sayfaları toplu olarak işlemeyi düşünün.

### Aspose.Words for .NET hakkında daha fazla bilgiyi nerede bulabilirim?  
 Şuna göz atın:[dokümantasyon](https://reference.aspose.com/words/net/) Kapsamlı kılavuzlar ve örnekler için.