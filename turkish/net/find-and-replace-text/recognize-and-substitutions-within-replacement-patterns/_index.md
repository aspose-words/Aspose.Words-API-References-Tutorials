---
title: Değiştirme Kalıpları İçindeki Değiştirmeleri Tanıma ve Değiştirme
linktitle: Değiştirme Kalıpları İçindeki Değiştirmeleri Tanıma ve Değiştirme
second_title: Aspose.Words for .NET API Referansı
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

 Bir belgemiz olduğunda, bir metin kullanarak metin ekleyebiliriz.`DocumentBuilder`nesne. Örneğimizde,`Write` "Jason, Paul'e biraz para verir" ifadesini ekleme yöntemi. :

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
