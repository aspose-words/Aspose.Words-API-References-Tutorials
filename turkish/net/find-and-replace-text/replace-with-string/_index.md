---
title: Dize ile Değiştir
linktitle: Dize ile Değiştir
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesindeki metni bir dizeyle nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/replace-with-string/
---
Bu makalede, Aspose.Words for .NET kitaplığında replace with String işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, bir Word belgesindeki belirli bir karakter dizisine dayalı olarak metin değiştirme gerçekleştirmenizi sağlar.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yeni Belge Oluşturma

 Dize değiştirmeyi kullanmaya başlamadan önce Aspose.Words for .NET kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2. Adım: Belgeye metin ekleyin

 Bir belgemiz olduğunda, bir metin kullanarak metin ekleyebiliriz.`DocumentBuilder` nesne. Örneğimizde,`Writeln` "üzgün, çılgın, kötü" ifadesini ekleme yöntemi:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## 3. Adım: Bir dizeyle değiştirin

 biz kullanıyoruz`Range.Replace`metni bir dizeyle değiştirme yöntemi. Örneğimizde, "üzgün" kelimesinin tüm oluşumlarını "kötü" ile değiştiriyoruz.`FindReplaceOptions` ile seçenek`FindReplaceDirection.Forward` arama yönü:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## 4. Adım: Düzenlenen belgeyi kaydetme

 Son olarak, değiştirilmiş belgeyi kullanarak belirtilen bir dizine kaydediyoruz.`Save` yöntem:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Aspose.Words for .NET kullanan replace with string için örnek kaynak kodu

Aspose.Words for .NET ile bir karakter dizisiyle değiştirmenin kullanımını gösteren tam örnek kaynak kodu burada:

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

Bu makalede, Aspose.Words for .NET'in String ile Değiştir işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, metin eklemek, bir dizeyle değiştirmek ve değiştirilen belgeyi kaydetmek için adım adım bir kılavuz izledik.

### SSS

#### S: Aspose.Words for .NET'teki "Dize İle Değiştir" işlevi nedir?

C: Aspose.Words for .NET'teki "Dizeyle Değiştir" işlevi, bir Word belgesindeki belirli bir karakter dizisine dayalı olarak metin değiştirme gerçekleştirmenize olanak tanır. Belirli bir dizgenin oluşumlarını bulmanızı ve bunları belirtilen başka bir diziyle değiştirmenizi sağlar.

#### S: Aspose.Words for .NET kullanarak nasıl yeni bir belge oluşturabilirim?

 C: Aspose.Words for .NET kullanarak yeni bir belge oluşturmak için`Document` nesne. İşte yeni bir belge oluşturmak için bir C# kodu örneği:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

#### S: Aspose.Words for .NET kullanarak bir belgeye nasıl metin ekleyebilirim?

 C: Bir belgeniz olduğunda, bir metin kullanarak metin ekleyebilirsiniz.`DocumentBuilder` nesne. Aspose.Words for .NET'te çeşitli yöntemleri kullanabilirsiniz.`DocumentBuilder` Farklı konumlara metin eklemek için sınıf. Örneğin,`Writeln` yeni bir satıra metin ekleme yöntemi. İşte bir örnek:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

#### S: Aspose.Words for .NET'te bir dizeyle metin değiştirmeyi nasıl yapabilirim?

 C: Aspose.Words for .NET'te bir dizgeyle metin değişimi gerçekleştirmek için`Range.Replace` yöntemini seçin ve değiştirilecek dizeyi ve onunla değiştirilecek dizeyi belirtin. Bu yöntem, basit bir metin eşleşmesi gerçekleştirir ve belirtilen dizenin tüm oluşumlarını değiştirir. İşte bir örnek:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### S: Aspose.Words for .NET'te "Replace With String" işleviyle büyük/küçük harfe duyarlı metin değişimi yapabilir miyim?

C: Evet, varsayılan olarak Aspose.Words for .NET'teki "Dizeyle Değiştir" işlevi büyük/küçük harfe duyarlıdır. Bu, yalnızca büyük/küçük harf açısından belirtilen dizeyle tam olarak eşleşen metni değiştireceği anlamına gelir. Büyük/küçük harfe duyarsız değiştirme yapmak istiyorsanız, değiştirilecek metni ve değiştirilen dizeyi aynı büyük/küçük harfe sahip olacak şekilde değiştirebilir veya normal ifadeler gibi diğer teknikleri kullanabilirsiniz.

#### S: Aspose.Words for .NET'teki "Dizeyle Değiştir" işlevini kullanarak bir belgedeki bir dizenin birden çok örneğini değiştirebilir miyim?

 C: Evet, Aspose.Words for .NET'teki "Dizeyle Değiştir" işlevini kullanarak bir belgedeki bir dizenin birden çok örneğini değiştirebilirsiniz. bu`Range.Replace` yöntem, belgenin içeriğinde belirtilen dizenin tüm oluşumlarını değiştirecektir.

#### S: Aspose.Words for .NET'te "Dizeyle Değiştir" işlevini kullanırken herhangi bir sınırlama veya dikkat edilmesi gereken nokta var mı?

C: Aspose.Words for .NET'te "Dize İle Değiştir" işlevini kullanırken, bağlamın farkında olmak ve değiştirmenin yalnızca istenildiği yerde uygulanmasını sağlamak önemlidir. Arama dizesinin, başka kelimelerin içinde veya özel biçimlendirmenin bir parçası olarak istenmeyen yerlerde görünmediğinden emin olun. Ek olarak, büyük belgelerle veya sık sık değiştirmelerle Sözcük İşleme yaparken performans üzerindeki etkileri göz önünde bulundurun.

#### S: Aspose.Words for .NET'teki "Replace With String" işlevini kullanarak farklı uzunluklardaki dizeleri değiştirebilir miyim?

C: Evet, Aspose.Words for .NET'teki "Replace With String" işlevini kullanarak farklı uzunluklardaki dizeleri değiştirebilirsiniz. Değiştirme dizesi herhangi bir uzunlukta olabilir ve arama dizesinin tam eşleşmesinin yerini alacaktır. Belge, yeni dizi uzunluğuna uyacak şekilde uygun şekilde ayarlanacaktır.