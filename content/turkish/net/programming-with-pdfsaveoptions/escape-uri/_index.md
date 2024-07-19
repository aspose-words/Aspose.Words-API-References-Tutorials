---
title: PDF Belgesinde URI'dan Kaçış
linktitle: PDF Belgesinde URI'dan Kaçış
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak PDF'lerdeki URI'lerden nasıl çıkış yapacağınızı öğrenin. Bu ayrıntılı kılavuz, süreç boyunca size adım adım yol gösterir.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/escape-uri/
---
## giriiş

Selam! Aspose.Words for .NET kullanarak bir Word belgesini PDF olarak kaydederken URI'lerin nasıl işleneceğini hiç merak ettiniz mi? Doğru yerdesiniz! Bugün, belgeniz dönüştürülürken bunların doğru şekilde çalıştığından emin olmak için PDF belgelerindeki kaçış URI'lerini derinlemesine inceleyeceğiz. Gelin bu yolculuğa adım adım birlikte çıkalım ve yol boyunca her konsepti kavramanızı sağlayın.

## Önkoşullar

Başlamadan önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Words for .NET: En son sürüme sahip olduğunuzdan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio veya başka herhangi bir .NET geliştirme ortamı.
3. Temel C# Bilgisi: Bu eğitimde, C# programlama konusunda temel bir anlayışa sahip olduğunuz varsayılmaktadır.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktarmanız gerekir. Aspose.Words işlevlerine erişim için bu çok önemlidir.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Tamam, hadi süreci sindirilebilir adımlara ayıralım. Takip edin ve kısa sürede URI'lerden kaçma konusunda profesyonel olacaksınız!

## 1. Adım: Belge Dizininizi Kurun

Koda dalmadan önce belgeler dizininizin yolunu ayarlayın. Dosyalarınızın kaydedileceği yer burasıdır.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`PDF belgenizi kaydetmek istediğiniz asıl yolla.

## Adım 2: Yeni Bir Belge Oluşturun

Daha sonra Aspose.Words'ü kullanarak yeni bir belge oluşturacağız. Bu belge, köprüler eklemek için tuvalimiz olarak hizmet edecektir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Burada,`Document` yeni Word belgenizdir ve`DocumentBuilder` belge oluşturma sürecini kolaylaştıran yardımcı bir sınıftır.

## 3. Adım: Köprü Ekleme

Şimdi belgeye bir köprü ekleyelim. Bu köprü, URI kaçış sürecimizin odak noktası olacaktır.

```csharp
builder.InsertHyperlink("Testlink", "https://www.google.com/search?q= aspose", false);
```

 Bu satırda,`"Testlink"` köprünün görüntü metnidir ve`"https://www.google.com/search?q= aspose"` URL'dir.`false` parametresi, bağlantının köprü olarak biçimlendirilmemesi gerektiğini belirtir (yani altı çizili ve mavi olmayacaktır).

## 4. Adım: Belgeyi PDF olarak kaydedin

Son olarak belgeyi PDF olarak kaydedin. Aspose.Words'ün PDF çıktısındaki URI'den kaçma işlemini burada halleder.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

 Bu satır, belgeyi dosya adıyla belirtilen dizine kaydeder.`WorkingWithPdfSaveOptions.EscapeUri.pdf`.

## Çözüm

İşte buyur! Aspose.Words for .NET kullanarak bir Word belgesini PDF olarak kaydederken URI'lerden nasıl kaçacağınızı öğrendiniz. Bu işlem, köprülerinizin sonuçtaki PDF'de işlevsel kalmasını ve düzgün biçimlendirilmiş olmasını sağlar. 

Bu küçük ama önemli tekniklerde uzmanlaşmanın belgelerinizin kalitesini ve işlevselliğini büyük ölçüde artırabileceğini unutmayın. Mutlu kodlama!

## SSS'ler

### Aspose.Words for .NET nedir?

Aspose.Words for .NET, geliştiricilerin .NET uygulamalarında Word belgeleri oluşturmasına, yönetmesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır.

### PDF'lerde URI'den kaçış neden önemlidir?

URI kaçışı, URL'lerdeki özel karakterlerin doğru şekilde yorumlanmasını sağlayarak bozuk bağlantıların önlenmesini ve bunların amaçlandığı gibi çalışmasını sağlar.

### Aspose.Words for .NET'te diğer bağlantı türlerini kullanabilir miyim?

Kesinlikle! Aspose.Words, dahili belge bağlantıları, yer imleri ve harici URL'ler dahil olmak üzere çeşitli bağlantı türlerini destekler.

### Aspose.Words for .NET'in ücretsiz deneme sürümünü nasıl edinebilirim?

 Ücretsiz deneme alabilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.Words for .NET hakkında daha ayrıntılı belgeleri nerede bulabilirim?

 Ayrıntılı belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/words/net/).
