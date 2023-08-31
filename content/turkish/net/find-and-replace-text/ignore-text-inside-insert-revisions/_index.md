---
title: Revizyon Ekleme İçindeki Metni Yoksay
linktitle: Revizyon Ekleme İçindeki Metni Yoksay
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'in Word belgelerindeki ekleme revizyonlarını değiştirmek için Aspose.Words for .NET'in "Revizyon Ekleme İçindeki Metni Yoksay" özelliğini nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

Bu makalede, Aspose.Words for .NET kütüphanesinde Revizyon Ekleme İçerisindeki Metni Yoksay fonksiyonunun nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, belgeleri düzenlerken düzeltme eklemelerin içindeki metni göz ardı etmek istediğimizde kullanışlıdır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## Adım 1: Yeni Bir Belge Oluşturma

 Insert revizyonlarının içindeki metni değiştirmeye başlamadan önce Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
Document doc = new Document();
```

## 2. Adım: Revizyon izlemeyle metin ekleyin

 Bir belgeye sahip olduğumuzda, bir düzeltme aracı kullanarak revizyon izlemeli metin ekleyebiliriz.`DocumentBuilder`nesne. Örneğin, revizyon izlemeyle "Eklendi" metnini eklemek için şunu kullanabiliriz:`StartTrackRevisions`, `Writeln` Ve`StopTrackRevisions` yöntemler:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## 3. Adım: İncelenmemiş metni ekleyin

 Revizyon izlemeli metne ek olarak, düzeltmeyi kullanarak düzeltilmemiş metni de ekleyebiliriz.`DocumentBuilder` nesne. Örneğin, "Metin" metnini düzeltmeden eklemek için şunu kullanabiliriz:`Write` yöntem:

```csharp
builder.Write("Text");
```

## Adım 4: Düzeltme Ekleme İçindeki Metni Yoksay işlevini kullanma

 Sonraki işlemlerde revizyon eklemelerin içindeki metni yok saymak için bir komut kullanabiliriz.`FindReplaceOptions` nesneyi ayarlayın ve`IgnoreInserted` mülkiyet`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## 5. Adım: Arama ve değiştirme için normal ifadeleri kullanma

Belge metninde arama işlemlerini ve değiştirme işlemlerini gerçekleştirmek için normal ifadeleri kullanacağız. Örneğimizde "e" harfinin geçtiği tüm yerleri arayacağız ve bunları yıldız işaretiyle değiştireceğiz "* ". .NET'i kullanacağız`Regex` bunun için sınıf:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Adım 6: Değiştirilen Belge Çıktısını Görüntüleme

Arama ve değiştirmeyi uyguladıktan sonra, belgenin değişen içeriğini aşağıdaki komutu kullanarak görüntüleyebiliriz:`GetText` yöntem:

```csharp
Console.WriteLine(doc.GetText());
```

## Adım 7: Revizyon Eklemeyi İçerecek Seçenekleri Değiştirme

Çıktı sonucunda, ekleme revizyonlarının içindeki metni dahil etmek istersek, ekleme revizyonlarını göz ardı etmeyecek şekilde seçenekleri değiştirebiliriz. Bunun için ayarlayacağız`IgnoreInserted` mülkiyet`false`:

```csharp
options.IgnoreInserted = false;
```

## Adım 8: Değiştirilen Belgeyi Ek Revizyonlarla Görüntüleme

Seçenekleri değiştirdikten sonra, ekleme revizyonlarının içindeki metni içeren sonucu elde etmek için arama yapabilir ve tekrar değiştirebiliriz:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Aspose.Words for .NET kullanarak Revizyon Ekleme İçerisindeki Metni Yoksay için örnek kaynak kodu

Aspose.Words for .NET ile İçerideki Metin Ekleme Revizyonlarını Yoksay işlevinin kullanımını gösteren tam örnek kaynak kodu:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// İzleme revizyonlarını içeren metin ekleyin.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Düzeltilmemiş metni ekleyin.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## Çözüm

Bu makalede, Aspose.Words for .NET'te Revizyon Ekleme İçerisindeki Metni Yoksay işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, izleme revizyonları ve düzeltilmemiş metin içeren metin eklemek, İçerideki Metni Göz ardı Etme Düzeltmeleri Ekle işlevini kullanmak, normal ifadelerle arama ve değiştirme işlemlerini gerçekleştirmek ve değiştirilen belgeyi görüntülemek için adım adım bir kılavuz izledik.

### SSS'ler

#### S: Aspose.Words for .NET'teki "Revizyon Ekleme İçindeki Metni Yoksay" özelliği nedir?

C: Aspose.Words for .NET'teki "Ekleme Revizyonlarının İçindeki Metni Yoksay" özelliği, metin bulma ve değiştirme gibi belirli işlemler sırasında ekleme revizyonlarının içindeki metnin göz ardı edilip edilmeyeceğini belirlemenize olanak tanır. Bu özellik etkinleştirildiğinde, ekleme revizyonlarının içindeki metin işlemler sırasında dikkate alınmaz.

#### S: Aspose.Words for .NET'i kullanarak nasıl yeni bir belge oluşturabilirim?

 C: Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmak için,`Document` nesne. Yeni bir belge oluşturmak için C# koduna bir örnek:

```csharp
Document doc = new Document();
```

#### S: Aspose.Words for .NET'te revizyon takibiyle nasıl metin ekleyebilirim?

C: Bir belgeye sahip olduğunuzda, bir düzeltme izleme aracı kullanarak metin ekleyebilirsiniz.`DocumentBuilder` nesne. Örneğin, revizyon izlemeyle "Eklendi" metnini eklemek için`StartTrackRevisions`, `Writeln` , Ve`StopTrackRevisions` yöntemler:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### S: Aspose.Words for .NET'e düzeltilmemiş metni nasıl ekleyebilirim?

 C: Revizyon izlemeli metne ek olarak, düzeltilmemiş metni de ekleyebilirsiniz.`DocumentBuilder` nesne. Örneğin, "Metin" metnini düzeltmeden eklemek için,`Write` yöntem:

```csharp
builder.Write("Text");
```

#### S: Aspose.Words for .NET'te revizyonların içindeki metni nasıl yok sayabilirim?

 C: Sonraki işlemler sırasında revizyon eklemelerin içindeki metni yok saymak için bir kullanabilirsiniz.`FindReplaceOptions` nesneyi ayarlayın ve`IgnoreInserted` mülkiyet`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
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

#### S: Aspose.Words for .NET'te çıktı sonucuna ekleme revizyonlarını nasıl ekleyebilirim?

 C: Çıktı sonucundaki ekleme revizyonlarının içindeki metni dahil etmek için, ekleme revizyonlarını göz ardı etmeyecek şekilde seçenekleri değiştirebilirsiniz. Bunun için ayarlayabilirsiniz`IgnoreInserted` mülkiyeti`FindReplaceOptions` itiraz etmek`false`:

```csharp
options.IgnoreInserted = false;
```

#### S: Aspose.Words for .NET'te ekleme revizyonları içeren değiştirilmiş belgeyi nasıl görüntüleyebilirim?

C: Revizyon ekleme seçeneklerini içerecek şekilde seçenekleri değiştirdikten sonra, ekleme revizyonlarının içindeki metni elde etmek için arama yapabilir ve tekrar değiştirebilirsiniz:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```