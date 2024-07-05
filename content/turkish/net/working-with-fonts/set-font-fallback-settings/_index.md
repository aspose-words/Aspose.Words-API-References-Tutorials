---
title: Yazı Tipi Geri Dönüş Ayarlarını Belirleyin
linktitle: Yazı Tipi Geri Dönüş Ayarlarını Belirleyin
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'te Font Geri Dönüş Ayarlarını nasıl ayarlayacağınızı öğrenin. Bu kapsamlı kılavuz, belgelerinizdeki tüm karakterlerin doğru şekilde görüntülenmesini sağlar.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-font-fallback-settings/
---

Farklı diller veya özel karakterler gibi çeşitli metin öğeleri içeren belgelerle çalışırken bu öğelerin doğru şekilde görüntülendiğinden emin olmak çok önemlidir. Aspose.Words for .NET, orijinal yazı tipi belirli karakterleri desteklemediğinde yazı tiplerinin değiştirilmesine ilişkin kuralların tanımlanmasına yardımcı olan Yazı Tipi Geri Dönüş Ayarları adı verilen güçlü bir özellik sunar. Bu kılavuzda, Aspose.Words for .NET kullanarak Font Geri Dönüş Ayarlarının nasıl kurulacağını adım adım eğitimle inceleyeceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

- Temel C# Bilgisi: C# programlama dili ve .NET çerçevesine aşinalık.
-  Aspose.Words for .NET: Buradan indirip yükleyin.[İndirme: {link](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Kodunuzu yazmak ve çalıştırmak için Visual Studio gibi bir kurulum.
-  Örnek Belge: Örnek bir belgeye sahip olun (örn.`Rendering.docx`) teste hazır.
- Yazı Tipi Geri Dönüş Kuralları XML: Yazı tipi geri dönüş kurallarını tanımlayan bir XML dosyası hazırlayın.

## Ad Alanlarını İçe Aktar

Aspose.Words'ü kullanmak için gerekli ad alanlarını içe aktarmanız gerekir. Bu, belge işleme için gereken çeşitli sınıflara ve yöntemlere erişim sağlar.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System;
```

## Adım 1: Belge Dizinini Tanımlayın

Öncelikle belgenizin saklandığı dizini tanımlayın. Bu, belgenizin bulunması ve işlenmesi için gereklidir.

```csharp
// Belgeler dizininin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belgeyi Yükleyin

 Belgenizi Aspose.Words'e yükleyin`Document` nesne. Bu adım, belgeyle programlı olarak çalışmanıza olanak tanır.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: Yazı Tipi Ayarlarını Yapılandırın

 Yeni bir tane oluştur`FontSettings` nesnesini kullanın ve yazı tipi geri dönüş ayarlarını bir XML dosyasından yükleyin. Bu XML dosyası, yazı tipi geri dönüşüne ilişkin kuralları içerir.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
```

## Adım 4: Yazı Tipi Ayarlarını Belgeye Uygulayın

 Yapılandırılmış olanı ata`FontSettings` belgeye. Bu, belge oluşturulurken yazı tipi geri dönüş kurallarının uygulanmasını sağlar.

```csharp
doc.FontSettings = fontSettings;
```

## Adım 5: Belgeyi Kaydedin

Son olarak belgeyi kaydedin. Yazı tipinin doğru şekilde değiştirilmesini sağlamak için kaydetme işlemi sırasında yazı tipi geri dönüş ayarları kullanılacaktır.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## XML Dosyası: Yazı Tipi Geri Dönüş Kuralları

Aşağıda, yazı tipi geri dönüş kurallarını tanımlayan XML dosyanızın nasıl görünmesi gerektiğine ilişkin bir örnek verilmiştir:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<FontFallbackSettings xmlns="Aspose.Words">
    <FallbackTable>
        <Rule Ranges="0B80-0BFF" FallbackFonts="Vijaya"/>
        <Rule Ranges="1F300-1F64F" FallbackFonts="Segoe UI Emoji, Segoe UI Symbol"/>
        <Rule Ranges="2000-206F, 2070-209F, 20B9" FallbackFonts="Arial" />
        <Rule Ranges="3040-309F" FallbackFonts="MS Gothic" BaseFonts="Times New Roman"/>
        <Rule Ranges="3040-309F" FallbackFonts="MS Mincho"/>
        <Rule FallbackFonts="Arial Unicode MS"/>
    </FallbackTable>
</FontFallbackSettings>
```

## Çözüm

Bu adımları izleyerek Aspose.Words for .NET'te Font Geri Dönüş Ayarlarını etkili bir şekilde ayarlayabilir ve kullanabilirsiniz. Bu, orijinal yazı tipi belirli karakterleri desteklemese bile belgelerinizin tüm karakterleri doğru şekilde görüntülemesini sağlar. Bu ayarların uygulanması belgelerinizin kalitesini ve okunabilirliğini büyük ölçüde artıracaktır.

## SSS

### S1: Yazı Tipi Geri Dönüşü nedir?

Yazı Tipi Geri Dönüşü, orijinal yazı tipi belirli karakterleri desteklemediğinde yazı tiplerinin değiştirilmesine olanak tanıyan ve tüm metin öğelerinin düzgün görüntülenmesini sağlayan bir özelliktir.

### S2: Birden fazla yedek yazı tipi belirtebilir miyim?

Evet, XML kurallarında birden çok yedek yazı tipi belirtebilirsiniz. Aspose.Words, karakteri destekleyen bir yazı tipi bulana kadar her yazı tipini belirtilen sırayla kontrol edecektir.

### S3: Aspose.Words for .NET'i nereden indirebilirim?

 adresinden indirebilirsiniz.[İndirme sayfasını düşünün](https://releases.aspose.com/words/net/).

### S4: Yazı tipi geri dönüş kuralları için XML dosyasını nasıl oluşturabilirim?

XML dosyası herhangi bir metin düzenleyici kullanılarak oluşturulabilir. Bu eğitimde verilen örnekte gösterilen yapıyı takip etmelidir.

### S5: Aspose.Words için destek mevcut mu?

 Evet, şuradan destek bulabilirsiniz:[Aspose.Words destek forumu](https://forum.aspose.com/c/words/8).