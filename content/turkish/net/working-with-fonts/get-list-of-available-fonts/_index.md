---
title: Mevcut Yazı Tiplerinin Listesini Alın
linktitle: Mevcut Yazı Tiplerinin Listesini Alın
second_title: Aspose.Words Belge İşleme API'si
description: Bu ayrıntılı adım adım eğitimde Aspose.Words for .NET kullanarak mevcut yazı tiplerinin bir listesini nasıl alacağınızı keşfedin. Yazı tipi yönetimi becerilerinizi geliştirin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/get-list-of-available-fonts/
---
## giriiş

Hiç kendinizi Word belgelerinizdeki yazı tiplerini yönetmekte zorlanırken buldunuz mu? Eğer bir .NET geliştiricisiyseniz Aspose.Words for .NET sizi kurtarmak için burada! Bu güçlü kitaplık yalnızca Word belgelerini programlı olarak oluşturmanıza ve değiştirmenize yardımcı olmakla kalmaz, aynı zamanda kapsamlı yazı tipi yönetimi yetenekleri de sunar. Bu kılavuzda, Aspose.Words for .NET kullanarak mevcut yazı tiplerinin listesini nasıl alacağınız konusunda size adım adım yol göstereceğiz. Kolayca takip edebilmenizi sağlamak için bunu sindirilebilir adımlara ayıracağız. O halde hemen konuya dalalım ve yazı tipi yönetimini çocuk oyuncağı haline getirelim!

## Önkoşullar

Başlamadan önce ihtiyacınız olacak birkaç şey var:

-  Aspose.Words for .NET: Aspose.Words for .NET kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
- Visual Studio: Bu örnek, geliştirme ortamı olarak Visual Studio'yu kullanır.
- .NET Framework: Makinenizde .NET Framework'ün kurulu olduğundan emin olun.
- Belge Dizini: Belgelerinizin saklandığı dizin yolu.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını projenize aktarın:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

## 1. Adım: Yazı Tipi Ayarlarını Başlatın

İlk adım yazı tipi ayarlarını başlatmaktır. Bu, belgeleriniz için yazı tipi kaynaklarını yönetmenize olanak tanır.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

- FontSettings: Bu sınıf, yazı tipi değiştirme ve yazı tipi kaynaklarına ilişkin ayarları belirtmek için kullanılır.
- fontSources: Mevcut font ayarlarından mevcut font kaynaklarının bir listesini oluşturuyoruz.

## Adım 2: Belge Dizinini Tanımlayın

Daha sonra belge dizininizin yolunu belirtin. Aspose.Words'ün yazı tiplerini arayacağı yer burasıdır.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: Bu dize değişkeni, yazı tiplerinizin bulunduğu dizinin yolunu tutar. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` gerçek yol ile.

## 3. Adım: Özel Yazı Tipi Klasörü Ekleyin

Şimdi Aspose.Words'e yazı tiplerini bu klasörde araması talimatını vermek için yeni bir klasör kaynağı ekleyin.

```csharp
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
```

- FolderFontSource: Bu sınıf bir klasör yazı tipi kaynağını temsil eder. İkinci parametre (`true`) alt klasörlerde yazı tiplerinin yinelemeli olarak aranıp aranmayacağını belirtir.

## 4. Adım: Yazı Tipi Kaynaklarını Güncelleyin

Özel yazı tipi klasörünü mevcut yazı tipi kaynakları listesine ekleyin ve yazı tipi ayarlarını güncelleyin.

```csharp
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

- fontSources.Add(folderFontSource): Özel yazı tipi klasörünü mevcut yazı tipi kaynaklarına ekler.
- güncellendiFontSources: Yazı tipi kaynaklarının listesini bir diziye dönüştürür.

## Adım 5: Yazı Tiplerini Alın ve Görüntüleyin

Son olarak mevcut yazı tiplerini alın ve ayrıntılarını görüntüleyin.

```csharp
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
    Console.WriteLine("Version  : " + fontInfo.Version);
    Console.WriteLine("FilePath : " + fontInfo.FilePath);
}
```

- GetAvailableFonts(): Güncellenen listedeki ilk yazı tipi kaynağından kullanılabilir yazı tiplerinin listesini alır.
-  fontInfo: Bir örneği`PhysicalFontInfo` Her yazı tipiyle ilgili ayrıntıları içerir.

## Çözüm

Tebrikler! Aspose.Words for .NET'i kullanarak mevcut yazı tiplerinin bir listesini başarıyla aldınız. Bu eğitim, yazı tipi ayarlarının başlatılmasından yazı tipi ayrıntılarının görüntülenmesine kadar her adımda size yol göstermiştir. Bu bilgiyle artık Word belgelerinizdeki yazı tiplerini kolaylıkla yönetebilirsiniz. Aspose.Words for .NET'in belge işleme yeteneklerinizi önemli ölçüde geliştirebilecek güçlü bir araç olduğunu unutmayın. Öyleyse devam edin ve geliştirme sürecinizi daha da verimli hale getirecek daha fazla özelliği keşfedin.

## SSS'ler

### Aspose.Words for .NET'i diğer .NET çerçeveleriyle kullanabilir miyim?
Evet, Aspose.Words for .NET, .NET Core ve .NET 5+ dahil olmak üzere çeşitli .NET çerçeveleriyle uyumludur.

### Aspose.Words for .NET'i nasıl yüklerim?
"Aspose.Words" ifadesini arayarak Visual Studio'daki NuGet Paket Yöneticisi aracılığıyla yükleyebilirsiniz.

### Birden fazla özel yazı tipi klasörü eklemek mümkün müdür?
 Evet, birden çok özel yazı tipi klasörü oluşturarak birden çok özel yazı tipi klasörü ekleyebilirsiniz.`FolderFontSource` örnekleri ve bunları yazı tipi kaynakları listesine ekleme.

### Belirli bir yazı tipi kaynağından yazı tipi ayrıntılarını alabilir miyim?
 Evet, yazı tipi kaynağının dizinini belirterek herhangi bir yazı tipi kaynağından yazı tipi ayrıntılarını alabilirsiniz.`updatedFontSources` sıralamak.

### Aspose.Words for .NET yazı tipi değiştirmeyi destekliyor mu?
Evet, orijinal yazı tipi mevcut olmasa bile metnin doğru şekilde oluşturulmasını sağlamak için yazı tipi değiştirmeyi destekler.