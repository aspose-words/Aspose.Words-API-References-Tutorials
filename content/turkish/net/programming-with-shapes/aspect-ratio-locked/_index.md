---
title: En Boy Oranı Kilitli
linktitle: En Boy Oranı Kilitli
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerindeki şekillerin en boy oranını nasıl kilitleyeceğinizi öğrenin. Resimlerinizi ve şekillerinizi orantılı tutmak için bu adım adım kılavuzu izleyin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/aspect-ratio-locked/
---
## giriiş

Word belgelerinizdeki görsellerin ve şekillerin mükemmel oranlarını nasıl koruyacağınızı hiç merak ettiniz mi? Bazen resimlerinizin ve şekillerinizin yeniden boyutlandırıldığında bozulmamasını sağlamanız gerekir. En boy oranını kilitlemenin kullanışlı olduğu yer burasıdır. Bu eğitimde Aspose.Words for .NET kullanarak Word belgelerindeki şekillerin en boy oranının nasıl ayarlanacağını inceleyeceğiz. Bu becerileri projelerinize güvenle uygulayabilmenizi sağlamak için bunu takip edilmesi kolay adımlara ayıracağız.

## Önkoşullar

Koda dalmadan önce, başlamak için neye ihtiyacınız olduğunu gözden geçirelim:

- Aspose.Words for .NET Library: Aspose.Words for .NET'in kurulu olması gerekir. Henüz yapmadıysanız, yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Bir .NET geliştirme ortamı kurduğunuzdan emin olun. Visual Studio popüler bir seçimdir.
- Temel C# Bilgisi: C# programlamaya biraz aşina olmak faydalı olacaktır.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktaralım. Bu ad alanları, Word belgeleri ve şekilleriyle çalışmak için ihtiyaç duyduğumuz sınıflara ve yöntemlere erişmemizi sağlayacaktır.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## 1. Adım: Belge Dizininizi Kurun

 Şekilleri değiştirmeye başlamadan önce belgelerimizin saklanacağı bir dizin oluşturmamız gerekiyor. Basitlik adına bir yer tutucu kullanacağız`YOUR DOCUMENT DIRECTORY`. Bunu belge dizininizin gerçek yoluyla değiştirin.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Yeni Bir Belge Oluşturun

Daha sonra Aspose.Words'ü kullanarak yeni bir Word belgesi oluşturacağız. Bu belge şekil ve görsel eklemek için tuvalimiz görevi görecek.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Burada bir örneğini oluşturuyoruz.`Document` sınıf ve kullanın`DocumentBuilder` belge içeriğini oluşturmamıza yardımcı olmak için.

## 3. Adım: Resim Ekleme

 Şimdi belgemize bir resim ekleyelim. biz kullanacağız`InsertImage` yöntemi`DocumentBuilder`sınıf. Belirttiğiniz dizinde bir görselin olduğundan emin olun.

```csharp
Shape shape = builder.InsertImage(dataDir + "Transparent background logo.png");
```

 Yer değiştirmek`dataDir + "Transparent background logo.png"` resim dosyanızın yolu ile birlikte.

## 4. Adım: En Boy Oranını Kilitleyin

Resim eklendikten sonra en boy oranını kilitleyebiliriz. En boy oranının kilitlenmesi, yeniden boyutlandırma sırasında görüntünün oranlarının sabit kalmasını sağlar.

```csharp
shape.AspectRatioLocked = true;
```

 Ayar`AspectRatioLocked` ile`true` görüntünün orijinal en boy oranını korumasını sağlar.

## Adım 5: Belgeyi Kaydedin

Son olarak belgeyi belirtilen dizine kaydedeceğiz. Bu adım, belge dosyasına yaptığımız tüm değişiklikleri yazar.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

## Çözüm

Tebrikler! Aspose.Words for .NET'i kullanarak Word belgelerindeki şekillerin en boy oranını nasıl ayarlayacağınızı başarıyla öğrendiniz. Bu adımları izleyerek görsellerinizin ve şekillerinizin orantılarını koruyarak belgelerinizin profesyonel ve gösterişli görünmesini sağlayabilirsiniz. En boy oranı kilitleme özelliğinin çeşitli senaryolarda nasıl çalıştığını görmek için farklı görseller ve şekillerle denemeler yapmaktan çekinmeyin.

## SSS'ler

### Kilitledikten sonra en boy oranının kilidini açabilir miyim?
Evet, ayarlayarak en boy oranının kilidini açabilirsiniz.`shape.AspectRatioLocked = false`.

### Kilitli en boy oranına sahip bir görüntüyü yeniden boyutlandırırsam ne olur?
Resim, orijinal genişlik-yükseklik oranını koruyarak orantılı olarak yeniden boyutlandırılacaktır.

### Bunu görsellerin yanı sıra diğer şekillere de uygulayabilir miyim?
Kesinlikle! En boy oranı kilitleme özelliği dikdörtgenler, daireler ve daha fazlası dahil olmak üzere herhangi bir şekle uygulanabilir.

### Aspose.Words for .NET, .NET Core ile uyumlu mu?
Evet, Aspose.Words for .NET hem .NET Framework hem de .NET Core'u destekler.

### Aspose.Words for .NET hakkında daha fazla belgeyi nerede bulabilirim?
 Kapsamlı belgeler bulabilirsiniz[Burada](https://reference.aspose.com/words/net/).