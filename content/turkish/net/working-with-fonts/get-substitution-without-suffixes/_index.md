---
title: Son Ekler Olmadan Değiştirme Alma
linktitle: Son Ekler Olmadan Değiştirme Alma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'te son ekler olmadan yazı tipi değiştirmeyi nasıl yöneteceğinizi öğrenin. Belgelerinizin her zaman mükemmel görünmesini sağlamak için adım adım kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/get-substitution-without-suffixes/
---

Aspose.Words for .NET kullanarak yazı tipi değiştirmeyi yönetmeye yönelik bu kapsamlı kılavuza hoş geldiniz. Belgelerinizde düzgün görünmeyen yazı tipleri ile sorun yaşadıysanız doğru yere geldiniz. Bu eğitim, sonekler olmadan yazı tipi değişimini verimli bir şekilde gerçekleştirmek için adım adım bir süreçten geçecektir. Başlayalım!

## Önkoşullar

Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Temel C# Bilgisi: C# programlamayı anlamak, adımları takip etmeyi ve uygulamayı kolaylaştıracaktır.
-  Aspose.Words for .NET Library: Kütüphaneyi şuradan indirip yükleyin:[İndirme: {link](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Kodunuzu yazmak ve çalıştırmak için Visual Studio gibi bir geliştirme ortamı kurun.
-  Örnek Belge: Örnek bir belge (örn.`Rendering.docx`) bu eğitim sırasında üzerinde çalışılacak.

## Ad Alanlarını İçe Aktar

Aspose.Words tarafından sağlanan sınıflara ve yöntemlere erişmek için öncelikle gerekli ad alanlarını içe aktarmamız gerekiyor.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using Aspose.Words.WarningInfo;
using System.Collections.Generic;
```

## Adım 1: Belge Dizinini Tanımlayın

Başlamak için belgenizin bulunduğu dizini belirtin. Bu, üzerinde çalışmak istediğiniz belgeyi bulmanıza yardımcı olur.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Değiştirme Uyarı İşleyicisini Ayarlayın

Daha sonra, belge işleme sırasında yazı tipi değişikliği gerçekleştiğinde bizi bilgilendirecek bir uyarı işleyicisi ayarlamamız gerekiyor. Bu, herhangi bir yazı tipi sorununu yakalamak ve ele almak için çok önemlidir.

```csharp
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
Document doc = new Document(dataDir + "Rendering.docx");
doc.WarningCallback = substitutionWarningHandler;
```

## 3. Adım: Özel Yazı Tipi Kaynakları Ekleme

Bu adımda Aspose.Words'ün doğru yazı tiplerini bulup kullanabilmesini sağlamak için özel yazı tipi kaynakları ekleyeceğiz. Bu, özellikle özel dizinlerde saklanan belirli yazı tipleriniz varsa kullanışlıdır.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());

FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

Bu kodda:
-  Mevcut yazı tipi kaynaklarını alıyoruz ve yenisini ekliyoruz`FolderFontSource` özel yazı tipi dizinimize işaret ederek (`C:\\MyFonts\\`).
- Daha sonra yazı tipi kaynaklarını bu yeni listeyle güncelliyoruz.

## Adım 4: Belgeyi Kaydedin

Son olarak yazı tipi değiştirme ayarlarını uyguladıktan sonra belgeyi kaydedin. Bu eğitim için onu PDF olarak kaydedeceğiz.

```csharp
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

## Adım 5: Uyarı İşleyicisi Sınıfını Oluşturun

 Uyarıları etkili bir şekilde işlemek için, aşağıdakileri uygulayan özel bir sınıf oluşturun:`IWarningCallback` arayüz. Bu sınıf, yazı tipi değiştirme uyarılarını yakalayacak ve günlüğe kaydedecektir.

```csharp
public class DocumentSubstitutionWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

Bu sınıfta:
- `Warning` yöntem, yazı tipi değişikliğiyle ilgili uyarıları yakalar.
- `FontWarnings` koleksiyon, daha fazla inceleme veya kayıt için bu uyarıları saklar.

## Çözüm

Artık Aspose.Words for .NET'i kullanarak son ekler olmadan yazı tipi değiştirme işleminde uzmanlaştınız. Bu bilgi, sistemde mevcut yazı tipleri ne olursa olsun belgelerinizin amaçlanan görünümünü korumasını sağlayacaktır. Aspose.Words'ün gücünden tam anlamıyla yararlanmak için farklı ayarlar ve kaynaklarla denemeler yapmaya devam edin.

## SSS

### S1: Birden çok özel dizindeki yazı tiplerini nasıl kullanabilirim?

 Birden fazla ekleyebilirsiniz`FolderFontSource` örnekler`fontSources`yazı tipi kaynaklarını buna göre listeleyin ve güncelleyin.

### S2: Aspose.Words for .NET'in ücretsiz deneme sürümünü nereden indirebilirim?

 Ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Ücretsiz deneme sayfasını aspose](https://releases.aspose.com/).

###  S3: kullanarak birden fazla uyarı türünü işleyebilir miyim?`IWarningCallback`?

 Evet`IWarningCallback` arayüz, yalnızca yazı tipi değişikliğini değil, çeşitli uyarı türlerini de yönetmenize olanak tanır.

### S4: Aspose.Words için nereden destek alabilirim?

 Destek için şu adresi ziyaret edin:[Aspose.Words destek forumu](https://forum.aspose.com/c/words/8).

### S5: Geçici lisans satın almak mümkün mü?

 Evet, geçici lisans alabilirsiniz.[geçici lisans sayfası](https://purchase.aspose.com/temporary-license/).