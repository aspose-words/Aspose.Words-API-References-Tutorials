---
title: Liste Girintisi İçin Düzey Başına Sekme Karakteri Kullan
linktitle: Liste Girintisi İçin Düzey Başına Sekme Karakteri Kullan
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak sekmeli girintili çok düzeyli listeler oluşturmayı öğrenin. Belgelerinizde kesin liste biçimlendirmesi için bu kılavuzu izleyin.
type: docs
weight: 10
url: /tr/net/programming-with-txtsaveoptions/use-tab-character-per-level-for-list-indentation/
---
## giriiş

İster bir rapor taslağı hazırlıyor olun, ister bir araştırma makalesi yazıyor olun, ister bir sunum hazırlıyor olun, listeler içeriğin düzenlenmesinde temeldir. Bununla birlikte, birden fazla girinti düzeyine sahip listeler sunmaya gelince, istenen formatı elde etmek biraz zor olabilir. Aspose.Words for .NET'i kullanarak liste girintisini kolayca yönetebilir ve her seviyenin nasıl temsil edildiğini özelleştirebilirsiniz. Bu öğreticide, hassas biçimlendirme için sekme karakterlerini kullanarak birden fazla girinti düzeyine sahip bir liste oluşturmaya odaklanacağız. Bu kılavuzun sonunda, belgenizi doğru girinti stiliyle nasıl ayarlayıp kaydedeceğiniz konusunda net bir anlayışa sahip olacaksınız.

## Önkoşullar

Adımlara geçmeden önce aşağıdakilerin hazır olduğundan emin olun:

1.  Aspose.Words for .NET Yüklü: Aspose.Words kütüphanesine ihtiyacınız var. Henüz yüklemediyseniz adresinden indirebilirsiniz.[İndirilenler](https://releases.aspose.com/words/net/).

2. C# ve .NET'in Temel Anlaşılması: C# programlama ve .NET çerçevesine aşinalık, bu eğitimi takip etmek için çok önemlidir.

3. Geliştirme Ortamı: C# kodunuzu yazmak ve yürütmek için bir IDE veya metin düzenleyiciniz olduğundan emin olun (örneğin, Visual Studio).

4. Örnek Belge Dizini: Belgenizi kaydedeceğiniz ve test edeceğiniz bir dizin oluşturun. 

## Ad Alanlarını İçe Aktar

Aspose.Words'ü .NET uygulamanızda kullanmak için öncelikle gerekli ad alanlarını içe aktarmanız gerekir. C# dosyanızın başına aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Bu bölümde Aspose.Words for .NET'i kullanarak sekmeli girintili çok düzeyli bir liste oluşturacağız. Şu adımları izleyin:

## 1. Adım: Belgenizi Ayarlayın

Yeni bir Belge ve DocumentBuilder Oluşturun

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni bir belge oluştur
Document doc = new Document();

// DocumentBuilder'ı başlat
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Burada yeni bir tane kurduk`Document` nesne ve bir`DocumentBuilder` Belge içinde içerik oluşturmaya başlamak için.

## 2. Adım: Varsayılan Liste Formatını Uygulayın

Listeyi Oluşturun ve Biçimlendirin

```csharp
// Listeye varsayılan numaralandırma stilini uygula
builder.ListFormat.ApplyNumberDefault();
```

Bu adımda varsayılan numaralandırma formatını listemize uyguluyoruz. Bu, daha sonra özelleştirebileceğimiz numaralı bir liste oluşturmamıza yardımcı olacaktır.

## 3. Adım: Farklı Düzeylerdeki Liste Öğelerini Ekleme

Liste Öğeleri Ekle ve Girinti Yap

```csharp
//İlk liste öğesini ekleyin
builder.Write("Element 1");

// İkinci düzeyi oluşturmak için girinti
builder.ListFormat.ListIndent();
builder.Write("Element 2");

// Üçüncü düzeyi oluşturmak için daha fazla girinti yapın
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

 Burada listemize her biri artan girinti düzeyine sahip üç öğe ekliyoruz.`ListIndent` yöntemi, sonraki her öğenin girinti düzeyini artırmak için kullanılır.

## 4. Adım: Kaydetme Seçeneklerini Yapılandırın

Sekme Karakterlerini Kullanmak İçin Girintiyi Ayarlama

```csharp
// Girinti için sekme karakterlerini kullanmak üzere kaydetme seçeneklerini yapılandırma
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';
```

 Biz yapılandırıyoruz`TxtSaveOptions` Kaydedilen metin dosyasındaki girinti için sekme karakterlerini kullanmak için.`ListIndentation.Character` özellik şu şekilde ayarlandı:`'\t'`, bir sekme karakterini temsil eder.

## Adım 5: Belgeyi Kaydedin

Belgeyi Belirtilen Seçeneklerle Kaydetme

```csharp
// Belgeyi belirtilen seçeneklerle kaydedin
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
```

 Son olarak belgeyi kullanarak kaydediyoruz.`Save` bizim özel yöntemimizle`TxtSaveOptions`. Bu, listenin girinti düzeyleri için sekme karakterleriyle kaydedilmesini sağlar.

## Çözüm

Bu eğitimde Aspose.Words for .NET'i kullanarak sekmeli girintili çok düzeyli bir liste oluşturmayı anlattık. Bu adımları izleyerek belgelerinizdeki listeleri kolayca yönetip biçimlendirebilir, bunların net ve profesyonel bir şekilde sunulmasını sağlayabilirsiniz. Raporlar, sunumlar veya başka herhangi bir belge türü üzerinde çalışıyor olsanız da, bu teknikler liste biçimlendirmeniz üzerinde hassas kontrol elde etmenize yardımcı olacaktır.

## SSS'ler

### Girinti karakterini sekmeden boşluğa nasıl değiştirebilirim?
 Değiştirebilirsiniz`saveOptions.ListIndentation.Character` Sekme yerine boşluk karakteri kullanma özelliği.

### Farklı düzeylere farklı liste stilleri uygulayabilir miyim?
Evet, Aspose.Words liste stillerinin çeşitli düzeylerde özelleştirilmesine olanak tanır. Farklı stiller elde etmek için liste biçimlendirme seçeneklerini değiştirebilirsiniz.

### Rakamlar yerine madde işaretleri kullanmam gerekirse ne olur?
 Kullanın`ListFormat.ApplyBulletDefault()` bunun yerine yöntem`ApplyNumberDefault()` madde işaretli bir liste oluşturmak için.

### Girinti için kullanılan sekme karakterinin boyutunu nasıl ayarlayabilirim?
 Maalesef sekme boyutu`TxtSaveOptions`sabittir. Girinti boyutunu ayarlamak için boşluk kullanmanız veya liste formatını doğrudan özelleştirmeniz gerekebilir.

### PDF veya DOCX gibi diğer formatlara dışa aktarırken bu ayarları kullanabilir miyim?
Belirli sekme karakteri ayarları metin dosyalarına uygulanır. PDF veya DOCX gibi formatlar için bu formatlardaki formatlama seçeneklerini ayarlamanız gerekir.