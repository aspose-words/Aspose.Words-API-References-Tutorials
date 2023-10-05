---
title: Dizeyle Değiştir
linktitle: Dizeyle Değiştir
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesindeki metni dizeyle nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/replace-with-string/
---
Bu makalede, Aspose.Words for .NET kütüphanesinde Change With String fonksiyonunun nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, bir Word belgesindeki belirli bir karakter dizisine dayalı olarak metin değiştirme işlemi gerçekleştirmenize olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## Adım 1: Yeni Bir Belge Oluşturma

 Dize değiştirmeyi kullanmaya başlamadan önce Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2. Adım: Belgeye metin ekleyin

 Bir belgeye sahip olduğumuzda, bir kullanarak metin ekleyebiliriz.`DocumentBuilder` nesne. Örneğimizde, şunu kullanıyoruz:`Writeln` "Üzgün, çılgın, kötü" ifadesini ekleme yöntemi:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## 3. Adım: Bir dizeyle değiştirin

 biz kullanıyoruz`Range.Replace`Metni bir dizeyle değiştirme yöntemi. Örneğimizde, "üzgün" kelimesinin tüm geçişlerini "kötü" ile değiştiriyoruz.`FindReplaceOptions` seçeneği ile`FindReplaceDirection.Forward` arama yönü:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## 4. Adım: Düzenlenen belgeyi kaydetme

Son olarak değiştirilen belgeyi aşağıdaki komutu kullanarak belirtilen dizine kaydederiz:`Save` yöntem:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Aspose.Words for .NET kullanan Change With String için örnek kaynak kodu

Aspose.Words for .NET ile bir karakter dizisinin değiştirilmesinin kullanımını gösteren tam örnek kaynak kodunu burada bulabilirsiniz:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Change With String fonksiyonunun nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, metin eklemek, bir dizeyle değiştirmek ve değiştirilen belgeyi kaydetmek için adım adım bir kılavuz izledik.

### SSS'ler

#### S: Aspose.Words for .NET'teki "Dizeyle Değiştir" işlevi nedir?

C: Aspose.Words for .NET'teki "Dizeyle Değiştir" işlevi, bir Word belgesindeki belirli bir karakter dizisine dayalı olarak metin değiştirme işlemi gerçekleştirmenize olanak tanır. Belirli bir dizenin oluşumlarını bulmanızı ve bunları belirtilen başka bir dizeyle değiştirmenizi sağlar.

#### S: Aspose.Words for .NET'i kullanarak nasıl yeni bir belge oluşturabilirim?

 C: Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmak için,`Document` nesne. Yeni bir belge oluşturmak için C# koduna bir örnek:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

#### S: Aspose.Words for .NET kullanarak bir belgeye nasıl metin ekleyebilirim?

 C: Bir belgeye sahip olduğunuzda, bir metin ekleyebilirsiniz.`DocumentBuilder` nesne. Aspose.Words for .NET'te çeşitli yöntemleri kullanabilirsiniz.`DocumentBuilder` farklı konumlara metin eklemek için sınıf. Örneğin, şunları kullanabilirsiniz:`Writeln` Yeni bir satıra metin ekleme yöntemi. İşte bir örnek:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

#### S: Aspose.Words for .NET'te bir dizeyle metin değiştirme işlemini nasıl gerçekleştirebilirim?

 C: Aspose.Words for .NET'te bir dizeyle metin değişimi gerçekleştirmek için şu komutu kullanabilirsiniz:`Range.Replace` yöntemini seçin ve değiştirilecek dizeyi ve değiştirilecek dizeyi belirtin. Bu yöntem basit bir metin eşleşmesi gerçekleştirir ve belirtilen dizenin tüm oluşumlarını değiştirir. İşte bir örnek:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### S: Aspose.Words for .NET'teki "Replace With String" fonksiyonuyla büyük/küçük harfe duyarlı metin değişimi gerçekleştirebilir miyim?

C: Evet, varsayılan olarak Aspose.Words for .NET'teki "Replace With String" işlevi büyük/küçük harfe duyarlıdır. Bu, yalnızca büyük/küçük harf açısından belirtilen dizeyle tam olarak eşleşen metni değiştireceği anlamına gelir. Büyük/küçük harfe duyarlı olmayan değiştirme gerçekleştirmek istiyorsanız, değiştirilecek metni ve değiştirilen dizeyi aynı büyük/küçük harfe sahip olacak şekilde değiştirebilir veya normal ifadeler gibi diğer teknikleri kullanabilirsiniz.

#### S: Aspose.Words for .NET'teki "Dizeyle Değiştir" işlevini kullanarak bir belgede bir dizenin birden fazla tekrarını değiştirebilir miyim?

 C: Evet, Aspose.Words for .NET'teki "Dizeyle Değiştir" işlevini kullanarak bir belgede bir dizenin birden fazla tekrarını değiştirebilirsiniz.`Range.Replace` yöntemi, belgenin içeriğinde belirtilen dizenin tüm oluşumlarını değiştirecektir.

#### S: Aspose.Words for .NET'te "Replace With String" fonksiyonunu kullanırken herhangi bir sınırlama veya dikkat edilmesi gereken nokta var mı?

C: Aspose.Words for .NET'te "Replace With String" işlevini kullanırken, bağlamın farkında olmak ve değiştirmenin yalnızca amaçlanan yerde uygulandığından emin olmak önemlidir. Arama dizesinin başka kelimelerin içinde veya özel biçimlendirmenin bir parçası gibi istenmeyen yerlerde görünmediğinden emin olun. Ayrıca, büyük belgelerle veya sık sık değiştirilen Kelime İşleme sırasında performans etkilerini de göz önünde bulundurun.

#### S: Aspose.Words for .NET'teki "Dizeyle Değiştir" işlevini kullanarak farklı uzunluklardaki dizeleri değiştirebilir miyim?

C: Evet, Aspose.Words for .NET'teki "Dizeyle Değiştir" işlevini kullanarak farklı uzunluklardaki dizeleri değiştirebilirsiniz. Değiştirme dizesi herhangi bir uzunlukta olabilir ve arama dizesinin tam eşleşmesinin yerine geçecektir. Belge yeni dize uzunluğuna uyum sağlayacak şekilde ayarlanacaktır.