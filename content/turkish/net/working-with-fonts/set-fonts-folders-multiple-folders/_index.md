---
title: Yazı Tiplerini Ayarlama Klasörleri Birden Çok Klasör
linktitle: Yazı Tiplerini Ayarlama Klasörleri Birden Çok Klasör
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak Word belgelerinizde birden fazla yazı tipi klasörünü nasıl ayarlayacağınızı öğrenin. Bu adım adım kılavuz, belgelerinizin tam olarak ihtiyacınız olan yazı tiplerini kullanmasını sağlar.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-fonts-folders-multiple-folders/
---
## giriiş

Word belgelerinizde birden fazla yazı tipi kaynağını nasıl yöneteceğinizi hiç merak ettiniz mi? Belki farklı klasörlere dağılmış bir yazı tipi koleksiyonunuz vardır ve belgelerinizin bunları sorunsuz bir şekilde kullanmasını sağlayacak bir yola ihtiyacınız vardır. Şanslısın! Bugün Aspose.Words for .NET'i kullanarak yazı tipi klasörlerini nasıl ayarlayacağımızı inceliyoruz. Bu kılavuz, belgelerinizin tam istediğiniz gibi görünmesini sağlayarak süreç boyunca size adım adım yol gösterecektir.

## Önkoşullar

Başlamadan önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım. İşte takip etmeniz gerekenler:

-  Aspose.Words for .NET: Henüz yapmadıysanız Aspose.Words for .NET'i indirip yükleyin. Alabilirsin[Burada](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Visual Studio veya herhangi bir .NET uyumlu geliştirme ortamı.
- Temel C# Bilgisi: C#'a biraz aşina olmak, örnekleri takip etmenize yardımcı olacaktır.
- Yazı Tipi Dosyaları: Yazı tipi dosyalarınızın kolayca erişebileceğiniz dizinlerde saklandığından emin olun.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını C# projenize aktaralım. Bu, ihtiyacınız olan tüm Aspose.Words işlevlerine erişmenizi sağlar.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Bu setle Aspose.Words for .NET'te font klasörlerini ayarlamak için adım adım kılavuza geçelim.

## 1. Adım: Belgenizi Yükleyin

Pekala, çalışmak istediğiniz Word belgesini yükleyerek başlayalım. Belge yolunun hazır olduğundan emin olun. Bu örnek için "Rendering.docx" adlı bir belge kullanacağız.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Burada belgeyi belirtilen dizinden yüklüyoruz. Yeterince basit, değil mi?

## Adım 2: FontSettings Nesnesi Oluşturun

 Daha sonra, bir oluşturmamız gerekiyor`FontSettings` nesne. Bu nesne belgemiz için yazı tipi kaynaklarını yönetmemizi sağlayacaktır.

```csharp
FontSettings fontSettings = new FontSettings();
```

 Bu`FontSettings`nesne hangi yazı tipi klasörlerinin kullanılacağını tanımlamamıza yardımcı olacaktır.

## 3. Adım: Yazı Tipi Klasörlerini Ayarlayın

Şimdi en önemli kısım geliyor; yazı tipi klasörlerini ayarlama. Yazı tiplerinizin bulunduğu dizinleri belirttiğiniz yer burasıdır. Bu örnekte "C:\MyFonts" konumunda yazı tiplerimiz var\" ve "D:\Çeşitli\Fontlar\".

```csharp
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

İkinci parametre (`true` ), bu klasörlerin varsayılan yazı tipi kaynaklarını geçersiz kılacağını belirtir. Sistem yazı tipi kaynaklarını da korumak istiyorsanız aşağıdakilerin bir kombinasyonunu kullanabilirsiniz:`GetFontSources`Ve`SetFontSources`.

## Adım 4: Yazı Tipi Ayarlarını Belgeye Uygulayın

Font klasörleri ayarlandığında bu ayarları belgemize uygulamamız gerekiyor. Bu, belgenin oluşturma sırasında belirtilen yazı tiplerini kullanmasını sağlar.

```csharp
doc.FontSettings = fontSettings;
```

## Adım 5: Belgeyi Kaydedin

Son olarak belgeyi kaydedelim. Yazı tiplerini çalışırken görmek için bunu PDF olarak kaydedeceğiz.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

Ve işte karşınızda! Belgeniz için birden çok yazı tipi klasörünü başarıyla ayarladınız.

## Çözüm

Belgelerinizdeki yazı tiplerini yönetmek göz korkutucu bir görev gibi görünebilir, ancak Aspose.Words for .NET ile bu çok kolay! Bu basit adımları izleyerek belgelerinizin profesyonel görünmesini ve tam olarak ihtiyacınız olan yazı tiplerini kullanmasını sağlayabilirsiniz. İster belirli bir markalama gerektiren bir proje üzerinde çalışıyor olun, ister yalnızca belgenizin görünümü üzerinde daha fazla kontrol sahibi olmak istiyor olun, yazı tipi klasörlerini ayarlamak, uzmanlaşmaya değer bir beceridir.

## SSS'ler

### Yazı tipi klasörleri için ağ yollarını kullanabilir miyim?
Evet, yazı tipi klasörleriniz için ağ yollarını kullanabilirsiniz. Yollara uygulamanızdan erişilebildiğinden emin olun.

### Belirtilen klasörlerde bir yazı tipi eksikse ne olur?
Bir yazı tipi eksikse Aspose.Words, belirtilen varsayılan yazı tipine geri döner veya yedek bir yazı tipi kullanır.

### Sistem yazı tiplerini geçersiz kılmadan yazı tipi klasörleri ekleyebilir miyim?
 Kesinlikle! Kullanmak`FontSettings.GetFontSources` mevcut kaynakları almak ve bunları kullanarak özel klasörlerinizle birleştirmek için`FontSettings.SetFontSources`.

### Ekleyebileceğim yazı tipi klasörü sayısında bir sınır var mı?
Yazı tipi klasörlerinin sayısında kesin bir sınırlama yoktur. Ancak, daha fazla klasör yazı tipi yükleme sürelerini artırabileceğinden performansa dikkat edin.

### Belgemde hangi yazı tiplerinin kullanıldığını nasıl kontrol edebilirim?
 Şunu kullanabilirsiniz:`FontSettings.GetFontsSources` Belgeniz için geçerli olarak ayarlanmış yazı tipi kaynaklarını alma ve inceleme yöntemini kullanın.