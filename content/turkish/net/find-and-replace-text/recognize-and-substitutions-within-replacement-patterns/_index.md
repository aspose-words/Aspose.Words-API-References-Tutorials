---
title: Değiştirme Modelleri İçinde Tanıma ve Değiştirmeler
linktitle: Değiştirme Modelleri İçinde Tanıma ve Değiştirmeler
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'te Word belgelerini değiştirmek için tanıma ve değiştirmelerle değiştirme modellerini nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

Bu makalede Aspose.Words for .NET kütüphanesinde Tanıma ve Değişim Modelleri İçinde Değiştirme fonksiyonunun nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, karmaşık arama kalıplarının tanınmasına ve belge işleme sırasında yakalanan gruplara göre değişiklik yapılmasına yardımcı olur.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## Adım 1: Yeni Bir Belge Oluşturma

Değiştirme modellerinde eşleşmeleri ve yer değiştirmeleri kullanmaya başlamadan önce Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
Document doc = new Document();
```

## 2. Adım: Belgeye metin ekleyin

 Bir belgeye sahip olduğumuzda, bir kullanarak metin ekleyebiliriz.`DocumentBuilder` nesne. Örneğimizde, şunu kullanıyoruz:`Write` "Jason, Paul'e biraz para veriyor." ifadesini ekleme yöntemi. :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## Adım 3: Değiştirme Modellerinde Tanımalar ve Değiştirmeler

 Şimdi şunu kullanacağız:`Range.Replace` belirli kalıpları tanımak için normal bir ifade kullanarak metin araması yapma ve değiştirme işlevi. Örneğimizde normal ifadeyi kullanıyoruz`([A-z]+) gives money to ([A-z]+)` Birinin başka birine para verdiği cümleleri tanımak. Değiştirme modelini kullanıyoruz`$2 takes money from $1` rolleri tersine çevirerek oyuncu değişikliğini gerçekleştirmek. Kullanımı`$1` Ve`$2` normal ifadenin yakaladığı grupları ifade eder:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Aspose.Words for .NET kullanarak Değiştirme Modelleri İçinde Tanıma ve Değiştirmeler için örnek kaynak kodu

Aspose.Words for .NET ile değiştirme modellerinde eşleşmelerin ve yer değiştirmelerin kullanımını gösteren örnek kaynak kodunun tamamı burada:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Değiştirme Modelleri İçinde Tanıma ve Değiştirme özelliğinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, metin eklemek, normal ifadeler ve yakalanan gruplara dayalı değiştirme kalıpları kullanarak arama ve değiştirme gerçekleştirmek ve belgeyi değiştirmek için adım adım bir kılavuz izledik.

### SSS'ler

#### S: Aspose.Words for .NET'teki "Değiştirme Modelleri İçinde Tanıma ve Değiştirme" özelliği nedir?

C: Aspose.Words for .NET'teki "Değiştirme Modelleri İçinde Tanıma ve Değiştirmeler" özelliği, düzenli ifadeler kullanarak karmaşık arama modellerini tanımanıza ve belge işleme sırasında yakalanan gruplara dayalı olarak değiştirmeler yapmanıza olanak tanır. Değiştirme modelinde yakalanan gruplara referans vererek eşleşen metni dinamik olarak dönüştürmenize olanak tanır.

#### S: Aspose.Words for .NET'i kullanarak nasıl yeni bir belge oluşturabilirim?

 C: Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmak için,`Document` nesne. Yeni bir belge oluşturmak için C# koduna bir örnek:

```csharp
Document doc = new Document();
```

#### S: Aspose.Words for .NET kullanarak bir belgeye nasıl metin ekleyebilirim?

 C: Bir belgeye sahip olduğunuzda, bir metin ekleyebilirsiniz.`DocumentBuilder` nesne. Örneğin, "Jason, Paul'a para veriyor." ifadesini eklemek için şu ifadeyi kullanabilirsiniz:`Write` yöntem:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### S: Aspose.Words for .NET'te normal ifadeleri kullanarak nasıl metin araması yapabilir ve değiştirebilirim?

 C: Aspose.Words for .NET'te normal ifadeler kullanarak metin araması yapmak ve değiştirmek için şu komutu kullanabilirsiniz:`Range.Replace` düzenli ifade modeliyle birlikte çalışır. Bir oluşturabilirsiniz`Regex` İstenilen desene sahip nesneyi ve onu iletin`Replace` yöntem:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### S: Aspose.Words for .NET'te metin arama ve değiştirme sırasında yakalanan grupları değiştirme modelinde nasıl kullanabilirim?

 C: Aspose.Words for .NET'te metin arama ve değiştirme sırasında yakalanan grupları değiştirme modelinde kullanmak için,`UseSubstitutions` mülkiyeti`FindReplaceOptions` nesne. Bu, aşağıdakileri kullanarak yakalanan gruplara referans vermenizi sağlar:`$1`, `$2`, vb. değiştirme modelinde:

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### S: Örnek kaynak kodu, Aspose.Words for .NET'teki "Değiştirme Modelleri İçinde Tanıma ve Değiştirmeler" özelliği için neyi gösteriyor?

C: Örnek kaynak kodu, Aspose.Words for .NET'teki "Değiştirme Modelleri İçinde Tanıma ve Değiştirme" özelliğinin kullanımını göstermektedir. Bir belgenin nasıl oluşturulacağını, metin ekleneceğini, metin aramasının nasıl gerçekleştirileceğini ve normal ifadeler kullanarak nasıl değiştirileceğini ve eşleşen metni dinamik olarak dönüştürmek için değiştirme modelinde yakalanan grupların nasıl kullanılacağını gösterir.

#### S: Aspose.Words for .NET'te düzenli ifadelerin kullanımına ilişkin daha fazla bilgi ve örneği nerede bulabilirim?

C: Aspose.Words for .NET'te normal ifadelerin kullanımına ilişkin daha fazla bilgi ve örnekler için şu adrese başvurabilirsiniz:[Aspose.Words for .NET API referansları](https://reference.aspose.com/words/net/). Belgeler, Aspose.Words for .NET'te düzenli ifadeler ve metin manipülasyonu içeren çeşitli senaryolar için ayrıntılı açıklamalar ve kod örnekleri sunmaktadır.

#### S: Metin arama ve değiştirme sırasında yakalanan gruplara göre belgenin diğer yönlerini değiştirebilir miyim?

C: Evet, metin arama ve değiştirme sırasında yakalanan gruplara göre belgenin diğer yönlerini değiştirebilirsiniz. Metin değişiklikleri yapmanın yanı sıra, Aspose.Words for .NET tarafından sağlanan çeşitli API'leri kullanarak formatı, stilleri, belge yapısını ve yakalanan gruplara dayalı diğer öğeleri değiştirebilirsiniz.

#### S: Aspose.Words for .NET'te normal ifadeleri ve yakalanan grupları kullanırken herhangi bir sınırlama veya dikkate alınması gereken noktalar var mı?

C: Düzenli ifadeler ve yakalanan gruplar, Aspose.Words for .NET'te metin arama ve değiştirme için güçlü yetenekler sunarken, karmaşıklık ve performans sonuçlarını dikkate almak önemlidir. Son derece karmaşık düzenli ifadeler ve çok sayıda yakalanan grup performansı etkileyebilir. Belgelerin verimli şekilde işlenmesini sağlamak amacıyla, belirli kullanım durumlarınız için normal ifadeleri test etmeniz ve optimize etmeniz önerilir.

#### S: "Değiştirme Modelleri İçinde Tanıma ve Değiştirme" özelliğini İngilizce dışındaki dillerde kullanabilir miyim?

C: Evet, Aspose.Words for .NET'in "Değiştirme Modelleri İçinde Tanıma ve Değiştirmeler" özelliği İngilizce dışındaki dillerle de kullanılabilir. Düzenli ifadeler dilden bağımsızdır ve herhangi bir dildeki belirli kalıplarla eşleşecek şekilde hazırlanabilir. Normal ifade modelini istediğiniz dile ve tanımak ve değiştirmek istediğiniz belirli metin kalıplarına uyacak şekilde ayarlayabilirsiniz.