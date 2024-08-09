---
title: Yazı Tipi Değiştirmeyi Devre Dışı Bırakmayı Etkinleştir
linktitle: Yazı Tipi Değiştirmeyi Devre Dışı Bırakmayı Etkinleştir
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerinde yazı tipi değiştirmeyi nasıl etkinleştireceğinizi veya devre dışı bırakacağınızı öğrenin. Belgelerinizin tüm platformlarda tutarlı görünmesini sağlayın.
type: docs
weight: 10
url: /tr/net/working-with-fonts/enable-disable-font-substitution/
---
## giriiş

Hiç kendinizi bir Word belgesinde titizlikle seçtiğiniz yazı tiplerinin başka bir bilgisayarda görüntülendiğinde değiştirildiği bir durumda buldunuz mu? Sinir bozucu, değil mi? Bunun nedeni, sistemin eksik bir yazı tipini kullanılabilir bir yazı tipiyle değiştirdiği bir işlem olan yazı tipi değiştirme işlemidir. Ama endişelenmeyin! Aspose.Words for .NET ile yazı tipi değişimini kolayca yönetebilir ve kontrol edebilirsiniz. Bu eğitimde, Word belgelerinizde yazı tipi değiştirmeyi etkinleştirme veya devre dışı bırakma adımlarında size yol göstererek belgelerinizin her zaman tam istediğiniz gibi görünmesini sağlayacağız.

## Önkoşullar

Adımlara geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

-  Aspose.Words for .NET: En son sürümü indirin[Burada](https://releases.aspose.com/words/net/).
- Visual Studio: .NET'i destekleyen herhangi bir sürüm.
- Temel C# bilgisi: Bu, kodlama örneklerini takip etmenize yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Başlamak için projenize gerekli ad alanlarının aktarıldığından emin olun. Bunları C# dosyanızın en üstüne ekleyin:

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Şimdi süreci basit, yönetilebilir adımlara ayıralım.

## 1. Adım: Projenizi Kurun

Öncelikle Visual Studio'da yeni bir proje oluşturun ve Aspose.Words for .NET kütüphanesine bir referans ekleyin. Henüz yapmadıysanız, şuradan indirin:[Web sitesi](https://releases.aspose.com/words/net/).

## 2. Adım: Belgenizi Yükleyin

Ardından, çalışmak istediğiniz belgeyi yükleyin. İşte bunu nasıl yapacağınız:

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile. Bu kod belgeyi belleğe yükler, böylece onu işleyebilirsiniz.

## 3. Adım: Yazı Tipi Ayarlarını Yapılandırın

 Şimdi bir oluşturalım`FontSettings` yazı tipi değiştirme ayarlarını yönetme nesnesi:

```csharp
FontSettings fontSettings = new FontSettings();
```

## Adım 4: Varsayılan Yazı Tipi Değiştirmeyi Ayarlayın

Varsayılan yazı tipi değişimini istediğiniz bir yazı tipine ayarlayın. Orijinal yazı tipi mevcut değilse bu yazı tipi kullanılacaktır:

```csharp
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

Bu örnekte varsayılan yazı tipi olarak Arial'ı kullanıyoruz.

## Adım 5: Yazı Tipi Bilgisi Değiştirmeyi Devre Dışı Bırakın

Sistemin eksik yazı tiplerini mevcut yazı tipleriyle değiştirmesini engelleyen yazı tipi bilgisi değiştirmeyi devre dışı bırakmak için aşağıdaki kodu kullanın:

```csharp
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
```

## Adım 6: Yazı Tipi Ayarlarını Belgeye Uygulayın

Şimdi bu ayarları belgenize uygulayın:

```csharp
doc.FontSettings = fontSettings;
```

## Adım 7: Belgenizi Kaydedin

Son olarak değiştirilen belgenizi kaydedin. İstediğiniz formatta kaydedebilirsiniz. Bu eğitim için onu PDF olarak kaydedeceğiz:

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```

## Çözüm

Ve işte karşınızda! Bu adımları izleyerek Aspose.Words for .NET'i kullanarak Word belgelerinizdeki yazı tipi değişimini kolayca kontrol edebilirsiniz. Bu, belgelerinizin nerede görüntülenirse görüntülensin amaçlanan görünüm ve hislerini korumasını sağlar.

## SSS'ler

### Değiştirmek için Arial dışındaki yazı tiplerini kullanabilir miyim?

 Kesinlikle! Yazı tipi adını değiştirerek sisteminizde bulunan herhangi bir yazı tipini belirleyebilirsiniz.`DefaultFontName` mülk.

### Belirtilen varsayılan yazı tipi mevcut değilse ne olur?

Varsayılan yazı tipi mevcut değilse Aspose.Words, uygun bir alternatif bulmak için sistem geri dönüş mekanizmasını kullanacaktır.

### Yazı tipi değiştirmeyi devre dışı bıraktıktan sonra tekrar etkinleştirebilir miyim?

 Evet, geçiş yapabilirsiniz`Enabled` mülkiyeti`FontInfoSubstitution` geri dönmek`true` yazı tipi değiştirmeyi tekrar etkinleştirmek istiyorsanız.

### Hangi yazı tiplerinin değiştirildiğini kontrol etmenin bir yolu var mı?

Evet, Aspose.Words, yazı tipi değişimini günlüğe kaydetme ve izleme yöntemleri sunarak hangi yazı tiplerinin değiştirildiğini görmenizi sağlar.

### Bu yöntemi DOCX dışında diğer belge formatları için de kullanabilir miyim?

Kesinlikle! Aspose.Words çeşitli formatları destekler ve bu yazı tipi ayarlarını desteklenen herhangi bir formata uygulayabilirsiniz.