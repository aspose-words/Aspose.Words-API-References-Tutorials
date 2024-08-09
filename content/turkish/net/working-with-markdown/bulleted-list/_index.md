---
title: Madde İşaretli Liste
linktitle: Madde İşaretli Liste
second_title: Aspose.Words Belge İşleme API'si
description: Bu adım adım kılavuzla Aspose.Words for .NET kullanarak Word belgelerinde madde işaretli listeler oluşturmayı ve özelleştirmeyi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/bulleted-list/
---
## giriiş

Aspose.Words for .NET dünyasına dalmaya hazır mısınız? Bugün, Word belgelerinizde madde işaretli bir liste oluşturmanın üzerinden geçeceğiz. İster fikirlerinizi düzenliyor, ister öğeleri listeliyor, ister yalnızca belgenize biraz yapı ekliyor olun, madde işaretli listeler son derece kullanışlıdır. Öyleyse başlayalım!

## Önkoşullar

Kodlama eğlencesine geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Words for .NET: Aspose.Words kütüphanesinin kurulu olduğundan emin olun. Henüz sahip değilseniz, yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio gibi AC# geliştirme ortamı.
3. Temel C# Bilgisi: C# programlamaya ilişkin temel bir anlayış, ilerlemenize yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktaralım. Bu, kodumuzun sorunsuz çalışması için gerekli ortamı hazırlamak gibidir.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Lists;
```

Şimdi süreci kolay, yönetilebilir adımlara ayıralım.

## 1. Adım: Yeni Bir Belge Oluşturun

Tamam, yeni bir belge oluşturarak başlayalım. Burası tüm sihrin gerçekleşeceği yer.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Adım 2: Madde İşaretli Liste Formatını Uygulayın

Daha sonra madde işaretli liste formatını uygulayacağız. Bu, belgeye madde işaretli bir liste başlatmak üzere olduğumuzu bildirir.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Adım 3: Madde İşareti Listesini Özelleştirin

Burada madde işareti listesini beğenimize göre özelleştireceğiz. Bu örnekte madde işareti olarak kısa çizgi (-) kullanacağız.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## 4. Adım: Liste Öğelerini Ekleme

Şimdi madde işaretli listemize bazı öğeler ekleyelim. Burası yaratıcı olabileceğiniz ve ihtiyacınız olan içeriği ekleyebileceğiniz yerdir.

```csharp
builder.Writeln("Item 1");
builder.Writeln("Item 2");
```

## Adım 5: Alt Öğeleri Ekleyin

İşleri daha ilginç hale getirmek için "Öğe 2"nin altına bazı alt öğeler ekleyelim. Bu, alt noktaların düzenlenmesine yardımcı olur.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
builder.ListFormat.ListOutdent(); // Ana liste düzeyine dön
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak bir Word belgesinde madde işaretli bir liste oluşturdunuz. Bu basit bir işlemdir ancak belgelerinizi düzenlemek için inanılmaz derecede güçlüdür. İster basit listeler, ister karmaşık iç içe geçmiş listeler oluşturuyor olun, Aspose.Words ihtiyacınızı karşılar.

İhtiyaçlarınıza uyacak farklı liste stillerini ve formatlarını denemekten çekinmeyin. Mutlu kodlama!

## SSS'ler

### Listede farklı madde işareti sembolleri kullanabilir miyim?
    Evet, madde işareti simgelerini değiştirerek özelleştirebilirsiniz.`NumberFormat` mülk.

### Daha fazla girinti düzeyini nasıl eklerim?
    Kullanın`ListIndent` daha fazla seviye ekleme yöntemi ve`ListOutdent` daha yüksek bir seviyeye geri dönmek için.

### Madde işareti ve numara listelerini karıştırmak mümkün mü?
   Kesinlikle! kullanarak madde işareti ve sayı formatları arasında geçiş yapabilirsiniz.`ApplyNumberDefault`Ve`ApplyBulletDefault` yöntemler.

### Liste öğelerindeki metne stil uygulayabilir miyim?
    Evet, liste öğeleri içindeki metne farklı stiller, yazı tipleri ve biçimlendirme uygulayabilirsiniz.`Font` mülkiyeti`DocumentBuilder`.

### Çok sütunlu madde işaretli listeyi nasıl oluşturabilirim?
   Her hücrenin ayrı bir madde işaretli liste içerdiği çok sütunlu listeler oluşturmak için tablo biçimlendirmesini kullanabilirsiniz.