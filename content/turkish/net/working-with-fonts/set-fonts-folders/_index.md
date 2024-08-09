---
title: Yazı Tipi Klasörlerini Ayarla
linktitle: Yazı Tipi Klasörlerini Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Bu kapsamlı, adım adım kılavuzla Aspose.Words for .NET'te özel yazı tipi klasörlerini nasıl ayarlayacağınızı öğrenin. Belge yazı tiplerini geliştirmek isteyen geliştiriciler için mükemmeldir.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-fonts-folders/
---
## giriiş

Selam! Aspose.Words for .NET'te özel yazı tipleri dünyasına dalmaya hazır mısınız? Hadi başlayalım. Bu eğitim, özel yazı tipi klasörleri ayarlama sürecinde size rehberlik edecek ve belgelerinizin tam istediğiniz gibi görünmesini sağlayacaktır. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu kılavuz size her adımda yol gösterecektir. O halde hadi bu yazı tiplerinin muhteşem görünmesini sağlayalım!

## Önkoşullar

Başlamadan önce, ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

-  Aspose.Words for .NET: Yapabilirsin[indirmek](https://releases.aspose.com/words/net/) eğer henüz yapmadıysanız.
- Visual Studio: Her sürüm çalışacaktır ancak en yenisi her zaman en iyisidir.
- Bir Belge: Bu eğitim için bir Word belgesi kullanacağız. Kendinizinkini oluşturabilir veya mevcut olanı kullanabilirsiniz.
- Özel Yazı Tipleri: Bazı özel yazı tiplerini hazır bulundurun. Bunları yazı tipi klasörlerinin nasıl ayarlanacağını göstermek için kullanacağız.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktaralım. Bu, Aspose.Words'ten ihtiyacımız olan sınıflara ve yöntemlere erişmek için gereklidir.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Bu ad alanlarının içe aktarılmasıyla özel yazı tipi klasörlerimizi oluşturmaya hazırız.

## 1. Adım: Belge Dizininizi Tanımlayın

 Belge dizininizin yolunu tanımlayarak başlayalım. Burası Word belgenizin saklandığı yerdir. Adlı bir değişken kullanacağız`dataDir` Bu yolu saklamak için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` Dizininizin gerçek yolu ile. Bu çok önemlidir çünkü Aspose.Words'ün belgenizi nerede bulacağını bilmesi gerekecektir.

## Adım 2: Yazı Tipi Kaynaklarını Ayarlayın

 Daha sonra yazı tipi kaynaklarını ayarlamamız gerekiyor. Burası Aspose.Words'e özel yazı tiplerimizi nerede bulacağını söylediğimiz yerdir. Bunu kullanacağız`FontSettings.DefaultInstance.SetFontsSources` bunu başarmanın yöntemi.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
});
```

İşte yaptığımız şey:

- SystemFontSource: Bu, Aspose.Words'e sistemin varsayılan yazı tiplerini kullanmasını söyler.
-  FolderFontSource: Özel yazı tiplerimizi içeren klasörü belirttiğimiz yerdir. Yer değiştirmek`"C:\\MyFonts\\"` özel yazı tipi dizininizin yolu ile.`true` parametresi alt dizinlerin de dahil edilmesi gerektiğini belirtir.

## 3. Adım: Belgenizi Yükleyin

Artık yazı tipi kaynaklarımızı ayarladığımıza göre çalışmak istediğimiz belgeyi yükleme zamanı geldi. biz kullanacağız`Document` Bunun için Aspose.Words'ten bir sınıf oluşturun.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 Şundan emin olun:`"Rendering.docx"` Word belgenizin adıdır. Belgenizin farklı bir adı varsa, bunu uygun şekilde güncellediğinizden emin olun.

## Adım 4: Belgenizi PDF Olarak Kaydedin

 Son olarak, özel yazı tiplerini çalışırken görmek için belgemizi PDF olarak kaydedelim. biz kullanacağız`Save` yöntemi`Document` sınıf.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

Bu, daha önce ayarladığımız özel yazı tiplerini kullanarak belgenizi belirtilen dizine PDF olarak kaydedecektir.

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'te özel yazı tipi klasörlerini başarıyla oluşturdunuz ve belgenizi bu özel yazı tipleriyle PDF olarak kaydettiniz. Oldukça hoş, değil mi? Yazı tiplerini özelleştirmek belgelerinizin görünümünde büyük bir fark yaratabilir ve artık bunu tam olarak nasıl yapacağınızı biliyorsunuz. Mutlu kodlama!

## SSS'ler

### Aspose.Words for .NET'i nasıl yüklerim?

 Yapabilirsiniz[indirmek](https://releases.aspose.com/words/net/) Aspose.Words for .NET'in en son sürümünü web sitesinden edinebilirsiniz.

### Birden fazla özel yazı tipi klasörü kullanabilir miyim?

 Evet, birden fazla ekleyebilirsiniz`FolderFontSource` örnekler`SetFontsSources`Farklı dizinlerdeki yazı tiplerini kullanma yöntemi.

### Sistem yazı tiplerini dahil etmek gerekli mi?

Sistem yazı tiplerinin dahil edilmesi isteğe bağlıdır ancak tüm standart yazı tiplerinin mevcut olduğundan emin olmak için önerilir.

### Aspose.Words hangi dosya türlerini destekliyor?

Aspose.Words, DOCX, DOC, PDF, TXT, HTML ve çok daha fazlasını içeren çok çeşitli dosya formatlarını destekler.

### Aspose.Words için nasıl geçici lisans alabilirim?

 Bir[geçici lisans](https://purchase.aspose.com/temporary-license/) Aspose.Words'ün tüm özelliklerini denemek için Aspose web sitesinden.