---
title: Yazı Tipi Vurgu İşaretini Ayarla
linktitle: Yazı Tipi Vurgu İşaretini Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Bu ayrıntılı, adım adım kılavuzla Aspose.Words for .NET kullanarak Word belgelerinde yazı tipi vurgu işaretlerini nasıl ayarlayacağınızı öğrenin. .NET geliştiricileri için mükemmel.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-font-emphasis-mark/
---
## giriiş

Bugünkü dersimizde Aspose.Words for .NET kullanarak bir Word belgesinde yazı tipi vurgu işaretlerinin nasıl ayarlanacağını detaylı olarak inceleyeceğiz. Belirli bir metnin altını benzersiz bir işaretle çizmek veya sadece belirli kelimeleri öne çıkarmak istiyorsanız, bu kılavuz size yardımcı olacaktır. O halde kemerinizi bağlayın ve başlayalım!

## Önkoşullar

Nitel ayrıntılara dalmadan önce aşağıdaki önkoşulların işaretlendiğinden emin olun:

-  Aspose.Words for .NET Library: Aspose.Words for .NET kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Visual Studio gibi çalışan bir geliştirme ortamı.
- .NET Framework: .NET Framework'ün kurulu olduğundan emin olun.

## Ad Alanlarını İçe Aktar

Aspose.Words for .NET ile çalışmak için gerekli ad alanlarını içe aktarmanız gerekir. Bunları kod dosyanızın en üstüne ekleyin:

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Şimdi süreci basit adımlara ayıralım. Word belgenizde yazı tipi vurgu işaretlerini ayarlamak için her adımı dikkatlice izleyin.

## 1. Adım: Document ve DocumentBuilder'ı başlatın

Öncelikle yeni bir belge ve DocumentBuilder'ı başlatmanız gerekir. DocumentBuilder sınıfı, belgeye metin ve diğer öğeleri eklemek için yöntemler sağlar.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni bir Belge başlat
Document document = new Document();

// DocumentBuilder'ı belgeyle başlat
DocumentBuilder builder = new DocumentBuilder(document);
```

## Adım 2: Yazı Tipi Vurgu İşaretini Ayarlayın

DocumentBuilder hazır olduğundan artık yazı tipi vurgu işaretini ayarlayabilirsiniz. Bu örnekte "UnderSolidCircle" vurgu işaretini kullanacağız.

```csharp
// Yazı tipi vurgu işaretini ayarlama
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;

// Vurgu işaretini içeren metni yazın
builder.Write("Emphasis text");
builder.Writeln();
```

## 3. Adım: Biçimlendirmeyi Temizleyin ve Normal Metin Ekleyin

Vurgu işaretini ayarladıktan sonra, herhangi bir vurgu olmadan normal bir metin eklemek isteyebilirsiniz. Bunun için biçimlendirmeyi temizlemeniz gerekir.

```csharp
// Yazı tipi formatını temizle
builder.Font.ClearFormatting();

// Normal metin yaz
builder.Write("Simple text");
```

## Adım 4: Belgeyi Kaydedin

İhtiyacınız olan tüm metni ve biçimlendirmeyi ekledikten sonra son adım belgeyi kaydetmektir. Belgenizi kaydetmek istediğiniz yolu ve dosya adını belirtin.

```csharp
// Belgeyi kaydet
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET kullanarak bir Word belgesinde yazı tipi vurgu işaretlerini ayarlamak bu kadar basittir. Yalnızca birkaç satır kodla metninizin öne çıkmasını sağlayabilir ve belgelerinize profesyonel bir dokunuş katabilirsiniz. İhtiyaçlarınıza uyacak farklı vurgu işaretlerini ve stillerini denemekten çekinmeyin.

## SSS'ler

### Yazı tipi vurgu işaretleri nelerdir?

Yazı tipi vurgu işaretleri, metnin öne çıkmasını sağlamak için metne eklenen özel simgelerdir. Noktalar, daireler ve diğer dekoratif işaretleri içerebilirler.

### Aspose.Words for .NET'te diğer vurgu işaretlerini kullanabilir miyim?

 Evet, Aspose.Words for .NET çeşitli vurgu işaretlerini destekler. adresine başvurarak farklı seçenekleri keşfedebilirsiniz.[dokümantasyon](https://reference.aspose.com/words/net/).

### Aspose.Words for .NET'in kullanımı ücretsiz mi?

 Aspose.Words for .NET tam işlevsellik için lisans gerektirir. Ücretsiz deneme alabilirsiniz[Burada](https://releases.aspose.com/) veya bir lisans satın alın[Burada](https://purchase.aspose.com/buy).

### Aspose.Words for .NET için nasıl destek alabilirim?

 Aspose topluluğundan ve destek ekibinden destek alabilirsiniz.[destek forumu](https://forum.aspose.com/c/words/8).

### Aspose.Words for .NET'i diğer .NET çerçeveleriyle kullanabilir miyim?

Evet, Aspose.Words for .NET, .NET Core ve .NET 5/6 dahil olmak üzere çeşitli .NET çerçeveleriyle uyumludur.