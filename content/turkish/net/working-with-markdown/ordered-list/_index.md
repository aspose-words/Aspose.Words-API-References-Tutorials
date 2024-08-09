---
title: Sıralı Liste
linktitle: Sıralı Liste
second_title: Aspose.Words Belge İşleme API'si
description: Adım adım kılavuzumuzla Aspose.Words for .NET kullanarak Word belgelerinde nasıl sıralı listeler oluşturacağınızı öğrenin. Belge oluşturmayı otomatikleştirmek için mükemmeldir.
type: docs
weight: 10
url: /tr/net/working-with-markdown/ordered-list/
---
## giriiş

Program aracılığıyla harika Word belgeleri oluşturmak için Aspose.Words for .NET'e dalmaya karar verdiniz. Harika seçim! Bugün, bir Word belgesinde sıralı bir listenin nasıl oluşturulacağını açıklayacağız. Bunu adım adım ilerleyeceğiz, bu nedenle ister kodlamaya yeni başlayan ister deneyimli bir profesyonel olun, bu kılavuzu son derece yararlı bulacaksınız. Hadi başlayalım!

## Önkoşullar

Koda dalmadan önce ihtiyacınız olacak birkaç şey var:

1. Aspose.Words for .NET: Aspose.Words for .NET'in kurulu olduğundan emin olun. Eğer yoksa indirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio veya herhangi bir .NET uyumlu IDE.
3. Temel C# Bilgisi: Kolayca takip edebileceğiniz C# temelleri konusunda rahat olmalısınız.

## Ad Alanlarını İçe Aktar

Aspose.Words'ü projenizde kullanmak için gerekli ad alanlarını içe aktarmanız gerekir. Bu, çalışmaya başlamadan önce alet kutunuzu kurmaya benzer.

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
```

Kodu küçük adımlara ayıralım ve her bir parçayı açıklayalım. Hazır? İşte başlıyoruz!

## 1. Adım: Belgeyi Başlatın

Öncelikle yeni bir belge oluşturmanız gerekir. Bunu bilgisayarınızda boş bir Word belgesi açmak gibi düşünün.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Burada yeni bir belgeyi ve DocumentBuilder nesnesini başlatıyoruz. DocumentBuilder kaleminiz gibidir ve belgeye içerik yazmanıza olanak tanır.

## 2. Adım: Numaralı Liste Formatını Uygulayın

Şimdi varsayılan numaralandırılmış liste formatını uygulayalım. Bu, Word belgenizi numaralı madde işaretleri kullanacak şekilde ayarlamaya benzer.

```csharp
builder.ListFormat.ApplyNumberDefault();
```

Bu kod satırı listenizin numaralandırmasını ayarlar. Kolay, değil mi?

## 3. Adım: Liste Öğelerini Ekleme

Sonra listemize bazı öğeler ekleyelim. Bir alışveriş listesini not ettiğinizi hayal edin.

```csharp
builder.Writeln("Item 1");
builder.Writeln("Item 2");
```

Bu satırlarla ilk iki maddeyi listenize eklemiş oluyorsunuz.

## Adım 4: Listeyi Girintilendirin

Bir öğenin altına alt öğeler eklemek isterseniz ne olur? Hadi yapalım!

```csharp
builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

`ListIndent` yöntem, bir alt liste oluşturarak listeyi girintiler. Artık daha çok iç içe geçmiş yapılacaklar listesi gibi hiyerarşik bir liste oluşturuyorsunuz.

## Çözüm

Bir Word belgesinde programlı olarak sıralı bir liste oluşturmak ilk başta göz korkutucu görünebilir, ancak Aspose.Words for .NET ile bu çok kolaydır. Bu basit adımları izleyerek belgelerinize kolayca liste ekleyebilir ve yönetebilirsiniz. İster rapor oluşturuyor olun, ister yapılandırılmış belgeler oluşturuyor olun, ister yalnızca iş akışlarınızı otomatikleştiriyor olun, Aspose.Words for .NET ihtiyacınızı karşılar. Peki neden bekleyelim? Kodlamaya başlayın ve sihrin ortaya çıktığını görün!

## SSS'ler

### Listenin numaralandırma stilini özelleştirebilir miyim?  
 Evet, numaralandırma stilini kullanarak özelleştirebilirsiniz.`ListFormat`özellikler. Romen rakamları, harfler vb. gibi farklı numaralandırma stillerini ayarlayabilirsiniz.

### Daha fazla girinti düzeyini nasıl eklerim?  
 Şunu kullanabilirsiniz:`ListIndent` Daha derin düzeyde alt listeler oluşturmak için yöntemi birden çok kez kullanın. Her çağrı`ListIndent` bir düzeyde girinti ekler.

### Madde işaretlerini ve numaralandırılmış listeleri karıştırabilir miyim?  
 Kesinlikle! kullanarak aynı belge içinde farklı liste formatlarını uygulayabilirsiniz.`ListFormat` mülk.

### Önceki listeden numaralandırmaya devam etmek mümkün mü?  
Evet, aynı liste formatını kullanarak numaralandırmaya devam edebilirsiniz. Aspose.Words, farklı paragraflardaki liste numaralandırmasını kontrol etmenize olanak tanır.

### Liste biçimini nasıl kaldırabilirim?  
 Liste formatını arayarak kaldırabilirsiniz.`ListFormat.RemoveNumbers()`. Bu, liste öğelerini tekrar normal paragraflara dönüştürecektir.