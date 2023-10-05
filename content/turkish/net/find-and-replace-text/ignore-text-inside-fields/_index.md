---
title: Alanların İçindeki Metni Yoksay
linktitle: Alanların İçindeki Metni Yoksay
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'in "Alanların İçindeki Metni Yoksay" özelliğini nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/ignore-text-inside-fields/
---
Bu makalede, Aspose.Words for .NET kütüphanesinde Alanların İçindeki Metni Yoksay fonksiyonunun nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, belgeleri düzenlerken alanların içindeki metni göz ardı etmek istediğimizde kullanışlıdır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## Adım 1: Yeni Bir Belge Oluşturma

 Alanların içindeki metinleri değiştirmeye başlamadan önce Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
Document doc = new Document();
```

## Adım 2: İçinde metin bulunan bir alan ekleme

 Bir belgeye sahip olduğumuzda, içine metin içeren bir alan ekleyebiliriz.`DocumentBuilder` nesne. Örneğin, "Alandaki metin" metnini içeren bir "INCLUDETEXT" alanı eklemek için şunu kullanabiliriz:`InsertField` yöntem:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## 3. Adım: Alanların İçindeki Metni Yoksay işlevini kullanma

 Sonraki işlemlerde alanların içindeki metni yok saymak için bir komut kullanabiliriz.`FindReplaceOptions` nesneyi ayarlayın ve`IgnoreFields`mülkiyet`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## 4. Adım: Arama ve değiştirme için normal ifadeleri kullanma

Belge metni üzerinde arama ve değiştirme işlemlerini gerçekleştirmek için normal ifadeleri kullanacağız. Örneğimizde "e" harfinin geçtiği tüm yerleri arayacağız ve bunları yıldız işaretiyle değiştireceğiz "* ". .NET'i kullanacağız`Regex` bunun için sınıf:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Adım 5: Değiştirilen Belge Çıktısını Görüntüleme

 Arama ve değiştirmeyi uyguladıktan sonra, belgenin değişen içeriğini aşağıdaki komutu kullanarak görüntüleyebiliriz:`GetText` yöntem:

```csharp
Console.WriteLine(doc.GetText());
```

## 6. Adım: Alanları dahil etmek için seçenekleri değiştirme

 çıktı sonucunda alanların içindeki metni dahil ederiz, alanları göz ardı etmeyecek şekilde seçenekleri değiştirebiliriz. Bunun için ayarlayacağız`IgnoreFields`mülkiyet`false`:

```csharp
options.IgnoreFields = false;
```

## Adım 7: Değiştirilen belgenin alanlarla birlikte görüntülenmesi

Seçenekleri değiştirdikten sonra, aramayı gerçekleştirebilir ve sonucu, dahil edilen alanların içindeki metinle elde etmek için yeniden değiştirebiliriz:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Aspose.Words for .NET kullanarak Alanların İçindeki Metni Yoksay için örnek kaynak kodu

Aspose.Words for .NET ile Alanların İçindeki Metni Yoksay işlevinin kullanımını gösteren tam örnek kaynak kodunu burada bulabilirsiniz:

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// İçinde metin bulunan alanı ekleyin.
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

Bu makalede, Aspose.Words for .NET'te Alanların İçindeki Metni Yoksay fonksiyonunun nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, içinde metin bulunan bir alan eklemek, Alanların İçindeki Metni Yoksay işlevini kullanmak, normal ifadelerle arama ve değiştirme işlemlerini gerçekleştirmek ve değiştirilen belgeyi görüntülemek için adım adım bir kılavuz izledik.

### SSS'ler

#### S: Aspose.Words for .NET'teki "Alanların İçindeki Metni Yoksay" özelliği nedir?

C: Aspose.Words for .NET'teki "Alanların İçindeki Metni Yoksay" özelliği, metin bulma ve değiştirme gibi belirli işlemler sırasında alanların içindeki metnin göz ardı edilip edilmeyeceğini belirlemenize olanak tanır. Bu özellik etkinleştirildiğinde, işlemler sırasında alanların içindeki metin dikkate alınmaz.

#### S: Aspose.Words for .NET'i kullanarak nasıl yeni bir belge oluşturabilirim?

 C: Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmak için,`Document` nesne. Yeni bir belge oluşturmak için C# koduna bir örnek:

```csharp
Document doc = new Document();
```

#### S: Aspose.Words for .NET kullanarak bir belgenin içine metin içeren bir alanı nasıl ekleyebilirim?

 C: Bir belgeye sahip olduğunuzda, içinde metin bulunan bir alanı kullanarak bir alan ekleyebilirsiniz.`DocumentBuilder` nesne. Örneğin, "Alandaki metin" metnini içeren bir "INCLUDETEXT" alanı eklemek için,`InsertField` yöntem:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

#### S: Aspose.Words for .NET'te alanların içindeki metni nasıl yok sayabilirim?

 C: Sonraki işlemler sırasında alanların içindeki metni yok saymak için`FindReplaceOptions` nesneyi ayarlayın ve`IgnoreFields`mülkiyet`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

#### S: Aspose.Words for .NET'te normal ifadeleri kullanarak nasıl arama ve değiştirme gerçekleştirebilirim?

 C: Düzenli ifadeler kullanarak belge metninde arama ve değiştirme işlemleri gerçekleştirmek için .NET'i kullanabilirsiniz.`Regex` sınıf. Örneğin, "e" harfinin geçtiği tüm yerleri aramak ve bunları yıldız işaretiyle değiştirmek için "* ", oluşturabilirsiniz`Regex` nesneyi kullanın ve şunu kullanın:`Replace` yöntem:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### S: Belgenin değiştirilmiş çıktısını Aspose.Words for .NET'te nasıl görüntüleyebilirim?

 C: Arama ve değiştirme işlemlerini uyguladıktan sonra belgenin değişen içeriğini`GetText` yöntem:

```csharp
Console.WriteLine(doc.GetText());
```

#### S: Aspose.Words for .NET'te çıktı sonucuna alanları nasıl ekleyebilirim?

 C: Çıktı sonucundaki alanların içindeki metni dahil etmek için, alanları göz ardı etmeyecek şekilde seçenekleri değiştirebilirsiniz. Bunun için ayarlayabilirsiniz`IgnoreFields` mülkiyeti`FindReplaceOptions` itiraz etmek`false`:

```csharp
options.IgnoreFields = false;
```

#### S: Değiştirilen belgeyi Aspose.Words for .NET'teki alanlarla nasıl görüntüleyebilirim?

C: Alanları dahil etme seçeneklerini değiştirdikten sonra, aramayı gerçekleştirebilir ve sonucu, dahil edilen alanların içindeki metinle elde etmek için yeniden değiştirebilirsiniz:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```