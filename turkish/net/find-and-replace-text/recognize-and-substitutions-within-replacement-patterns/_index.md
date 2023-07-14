---
title: Değiştirme Kalıpları İçindeki Değiştirmeleri Tanıma ve Değiştirme
linktitle: Değiştirme Kalıpları İçindeki Değiştirmeleri Tanıma ve Değiştirme
second_title: Aspose.Words Belge İşleme API'sı
description: Word belgelerini işlemek için Aspose.Words for .NET'te tanıma ve ikamelerle değiştirme modellerini nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

Bu makalede, Aspose.Words for .NET kitaplığındaki Regnize And Substitutions Within Değiştirme Kalıpları işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, karmaşık arama modellerinin tanınmasına ve belge manipülasyonu sırasında yakalanan gruplara göre değiştirmelerin gerçekleştirilmesine yardımcı olur.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yeni Belge Oluşturma

Değiştirme kalıplarında eşleştirmeleri ve ikameleri kullanmaya başlamadan önce, Aspose.Words for .NET kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
Document doc = new Document();
```

## 2. Adım: Belgeye metin ekleyin

 Bir belgemiz olduğunda, bir metin kullanarak metin ekleyebiliriz.`DocumentBuilder` nesne. Örneğimizde,`Write` "Jason, Paul'e biraz para verir" ifadesini ekleme yöntemi. :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## 3. Adım: Değiştirme Modellerinde Tanımalar ve Değiştirmeler

 Şimdi kullanacağız`Range.Replace` belirli kalıpları tanımak için normal bir ifade kullanarak metin arama ve değiştirme işlevi. Örneğimizde, normal ifadeyi kullanıyoruz`([A-z]+) gives money to ([A-z]+)` birinin başkasına para verdiği cümleleri tanımak. Değiştirme modelini kullanıyoruz`$2 takes money from $1` rolleri tersine çevirerek ikameyi gerçekleştirmek. Kullanımı`$1` Ve`$2` normal ifade tarafından yakalanan grupları ifade eder:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Aspose.Words for .NET kullanarak Değiştirme Modelleri İçinde Tanıma ve Değiştirmeler için örnek kaynak kodu

Aspose.Words for .NET ile değiştirme modellerinde eşleşmelerin ve ikamelerin kullanımını gösteren tam örnek kaynak kodu burada:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Değiştirme Modelleri İçinde Tanı ve Değiştirme özelliğinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, metin eklemek, düzenli ifadeler ve yakalanan gruplara dayalı değiştirme kalıplarını kullanarak arama ve değiştirme gerçekleştirmek ve belgeyi değiştirmek için adım adım bir kılavuz izledik.

### SSS

#### S: Aspose.Words for .NET'teki "Değiştirme Kalıpları İçinde Tanınma ve Değiştirmeler" özelliği nedir?

C: Aspose.Words for .NET'teki "Değiştirme Kalıpları İçinde Yer Değiştirmeleri Tanıyın" özelliği, düzenli ifadeler kullanarak karmaşık arama kalıplarını tanımanıza ve belge manipülasyonu sırasında yakalanan gruplara dayalı olarak değiştirmeler gerçekleştirmenize olanak tanır. Değiştirme modelinde yakalanan gruplara başvurarak eşleşen metni dinamik olarak dönüştürmenize olanak tanır.

#### S: Aspose.Words for .NET kullanarak nasıl yeni bir belge oluşturabilirim?

 C: Aspose.Words for .NET kullanarak yeni bir belge oluşturmak için`Document` nesne. İşte yeni bir belge oluşturmak için bir C# kodu örneği:

```csharp
Document doc = new Document();
```

#### S: Aspose.Words for .NET kullanarak bir belgeye nasıl metin ekleyebilirim?

 C: Bir belgeniz olduğunda, bir metin kullanarak metin ekleyebilirsiniz.`DocumentBuilder` nesne. Örneğin, "Jason, Paul'a para veriyor." ifadesini eklemek için`Write` yöntem:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### S: Aspose.Words for .NET'te normal ifadeleri kullanarak metin arama ve değiştirmeyi nasıl yapabilirim?

 C: Aspose.Words for .NET'te normal ifadeler kullanarak metin araması yapmak ve değiştirmek için`Range.Replace` düzenli bir ifade modeliyle birlikte işlev görür. oluşturabilirsiniz`Regex` istediğiniz desene sahip nesneyi seçin ve`Replace` yöntem:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### S: Aspose.Words for .NET'te metin arama ve değiştirme sırasında yakalanan grupları değiştirme modelinde nasıl kullanabilirim?

 C: Aspose.Words for .NET'te metin arama ve değiştirme sırasında değiştirme modelinde yakalanan grupları kullanmak için`UseSubstitutions`mülkiyeti`FindReplaceOptions` nesne. Bu, kullanarak yakalanan gruplara başvurmanıza izin verir.`$1`, `$2`, vb.

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### S: Aspose.Words for .NET'teki "Değiştirme Modelleri İçinde Tanınma ve Değiştirmeler" özelliği için örnek kaynak kodu neyi gösteriyor?

Y: Örnek kaynak kodu, Aspose.Words for .NET'teki "Değiştirme Modelleri İçinde Tanınma ve Değiştirmeler" özelliğinin kullanımını gösterir. Bir belgenin nasıl oluşturulacağını, metin ekleneceğini, normal ifadeler kullanılarak metin arama ve değiştirme işleminin nasıl gerçekleştirileceğini ve eşleşen metni dinamik olarak dönüştürmek için değiştirme modelinde yakalanan grupların nasıl kullanılacağını gösterir.

#### S: Aspose.Words for .NET'te düzenli ifadelerin kullanımına ilişkin daha fazla bilgiyi ve örneği nerede bulabilirim?

C: Aspose.Words for .NET'te düzenli ifadelerin kullanımına ilişkin daha fazla bilgi ve örnek için resmi belgelere ve Aspose.Words GitHub deposuna başvurabilirsiniz. Dokümantasyon, Aspose.Words for .NET'te düzenli ifadeler ve metin manipülasyonu içeren çeşitli senaryolar için ayrıntılı açıklamalar ve kod örnekleri sağlar.

#### S: Metin arama ve değiştirme sırasında yakalanan gruplara dayalı olarak belgenin diğer yönlerini değiştirebilir miyim?

C: Evet, metin arama ve değiştirme sırasında yakalanan gruplara dayalı olarak belgenin diğer yönlerini değiştirebilirsiniz. Metin değiştirme gerçekleştirmeye ek olarak, Aspose.Words for .NET tarafından sağlanan çeşitli API'leri kullanarak, yakalanan gruplara dayalı olarak biçimlendirmeyi, stilleri, belge yapısını ve diğer öğeleri değiştirebilirsiniz.

#### S: Aspose.Words for .NET'te normal ifadeleri ve yakalanan grupları kullanırken herhangi bir sınırlama veya dikkat edilmesi gereken nokta var mı?

C: Düzenli ifadeler ve yakalanan gruplar, Aspose.Words for .NET'te metin arama ve değiştirme için güçlü yetenekler sunarken, karmaşıklığı ve performans sonuçlarını dikkate almak önemlidir. Son derece karmaşık normal ifadeler ve çok sayıda yakalanan grup, performansı etkileyebilir. Verimli belge manipülasyonu sağlamak için normal ifadeleri belirli kullanım durumlarınız için test etmeniz ve optimize etmeniz önerilir.

#### S: "Değiştirme Modelleri İçinde Tanıma ve Değiştirme" özelliğini İngilizce dışındaki dillerde kullanabilir miyim?

C: Evet, Aspose.Words for .NET'teki "Recognize And Substitutions With Değiştirme Modelleri" özelliği İngilizce dışındaki dillerde kullanılabilir. Normal ifadeler dilden bağımsızdır ve herhangi bir dildeki belirli kalıplarla eşleşecek şekilde hazırlanabilir. Normal ifade kalıbını, istediğiniz dile ve tanımak ve değiştirmek istediğiniz belirli metin kalıplarına uyacak şekilde ayarlayabilirsiniz.