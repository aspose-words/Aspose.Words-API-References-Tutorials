---
title: Alanların İçindeki Metni Yoksay
linktitle: Alanların İçindeki Metni Yoksay
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET'in "Alanların İçindeki Metni Yoksay" özelliğini nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/ignore-text-inside-fields/
---
Bu makalede, Aspose.Words for .NET kitaplığındaki Alanların İçindeki Metni Yoksay işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, belgeleri işlerken alanların içindeki metni yok saymak istediğimizde kullanışlıdır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yeni Belge Oluşturma

 Alanların içindeki metni manipüle etmeye başlamadan önce, Aspose.Words for .NET kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
Document doc = new Document();
```

## 2. Adım: İçinde metin bulunan bir alan ekleme

 Bir belgemiz olduğunda, içine metin içeren bir alan ekleyebiliriz.`DocumentBuilder` nesne. Örneğin, "Text in field" metnini içeren bir "INCLUDETEXT" alanı eklemek için şunu kullanabiliriz:`InsertField` yöntem:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## 3. Adım: Alanların İçindeki Metni Yoksay işlevini kullanma

 Sonraki işlemlerde alanların içindeki metni yoksaymak için bir`FindReplaceOptions` nesne ve ayarlayın`IgnoreFields` mülkiyet`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## 4. Adım: Arama ve değiştirme için normal ifadeleri kullanma

Belge metni üzerinde arama ve değiştirme işlemlerini gerçekleştirmek için normal ifadeler kullanacağız. Örneğimizde, "e" harfinin geçtiği tüm yerleri arayacağız ve bunları bir yıldız işaretiyle değiştireceğiz "* ".NET'leri kullanacağız`Regex` Bunun için sınıf:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Adım 5: Değiştirilmiş Belge Çıktısını Görüntüleme

Ara ve değiştir işlemini uyguladıktan sonra, belgenin değişen içeriğini kullanarak görüntüleyebiliriz.`GetText` yöntem:

```csharp
Console.WriteLine(doc.GetText());
```

## 6. Adım: Alanları dahil etmek için seçenekleri değiştirme

çıktı sonucuna alanların içindeki metni dahil ediyoruz, alanları yok saymamak için seçenekleri değiştirebiliyoruz. Bunun için ayarlayacağımız`IgnoreFields` mülkiyet`false`:

```csharp
options.IgnoreFields = false;
```

## Adım 7: Değiştirilen belgeyi alanlarla birlikte görüntüleme

Seçenekleri değiştirdikten sonra, içerilen alanların içindeki metinle sonucu almak için aramayı tekrar yapabilir ve değiştirebiliriz:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Aspose.Words for .NET kullanarak Alanların İçindeki Metni Yoksay için örnek kaynak kodu

Aspose.Words for .NET ile Alanların İçindeki Metni Yoksay işlevinin kullanımını gösteren tam örnek kaynak kodu burada:

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// İçinde metin bulunan alan ekleyin.
	builder.InsertField("INCLUDETEXT", "Text in field");
	
	FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
	
	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreFields = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
  
```

## Çözüm

Bu makalede, Aspose.Words for .NET'te Alanların İçindeki Metni Yoksay işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, içinde metin bulunan bir alan eklemek, Alanların İçindeki Metni Yoksay işlevini kullanmak, normal ifadelerle arama ve değiştirme işlemlerini gerçekleştirmek ve değiştirilen belgeyi görüntülemek için adım adım bir kılavuz izledik.

### SSS

#### S: Aspose.Words for .NET'teki "Alanların İçindeki Metni Yoksay" özelliği nedir?

A: Aspose.Words for .NET'teki "Alanların İçindeki Metni Yoksay" özelliği, metin bulma ve değiştirme gibi belirli işlemler sırasında alanların içindeki metnin göz ardı edilip edilmeyeceğini belirlemenizi sağlar. Bu özellik etkinleştirildiğinde, alanların içindeki metin işlemler sırasında dikkate alınmaz.

#### S: Aspose.Words for .NET kullanarak nasıl yeni bir belge oluşturabilirim?

 C: Aspose.Words for .NET kullanarak yeni bir belge oluşturmak için`Document` nesne. İşte yeni bir belge oluşturmak için bir C# kodu örneği:

```csharp
Document doc = new Document();
```

#### S: Aspose.Words for .NET kullanarak bir belgenin içine metin içeren bir alanı nasıl ekleyebilirim?

 C: Bir belgeniz olduğunda, içinde metin bulunan bir alan ekleyebilirsiniz.`DocumentBuilder` nesne. Örneğin, "Alandaki metin" metnini içeren bir "INCLUDETEXT" alanı eklemek için,`InsertField` yöntem:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

#### S: Aspose.Words for .NET'te alanların içindeki metni nasıl yok sayabilirim?

A: Sonraki işlemler sırasında alanların içindeki metni yoksaymak için bir`FindReplaceOptions` nesne ve ayarlayın`IgnoreFields` mülkiyet`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

#### S: Aspose.Words for .NET'te normal ifadeleri kullanarak nasıl arama ve değiştirme yapabilirim?

 A: Normal ifadeleri kullanarak belgenin metninde arama ve değiştirme işlemlerini gerçekleştirmek için .NET'i kullanabilirsiniz.`Regex` sınıf. Örneğin, "e" harfinin tüm oluşumlarını aramak ve bunları bir yıldız işaretiyle değiştirmek için "* " oluşturabilirsiniz`Regex` nesne ve onunla birlikte kullanın`Replace` yöntem:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### S: Belgenin değiştirilmiş çıktısını Aspose.Words for .NET'te nasıl görüntüleyebilirim?

 C: Ara ve değiştir işlemlerini uyguladıktan sonra, belgenin değişen içeriğini aşağıdaki düğmeyi kullanarak görüntüleyebilirsiniz:`GetText` yöntem:

```csharp
Console.WriteLine(doc.GetText());
```

#### S: Aspose.Words for .NET'te çıktı sonucundaki alanları nasıl dahil edebilirim?

 A: Çıktı sonucuna alanların içindeki metni dahil etmek için, alanları göz ardı etmemek için seçenekleri değiştirebilirsiniz. Bunun için ayarlayabilirsiniz`IgnoreFields`mülkiyeti`FindReplaceOptions` itiraz etmek`false`:

```csharp
options.IgnoreFields = false;
```

#### S: Değiştirilen belgeyi Aspose.Words for .NET'teki alanlarla nasıl görüntüleyebilirim?

A: Alanları dahil etmek için seçenekleri değiştirdikten sonra, dahil edilen alanların içindeki metinle sonucu almak için arama ve değiştirme işlemini tekrar yapabilirsiniz:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```