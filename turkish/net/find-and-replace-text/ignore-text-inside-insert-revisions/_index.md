---
title: Ekleme Revizyonlarının İçindeki Metni Yoksay
linktitle: Ekleme Revizyonlarının İçindeki Metni Yoksay
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'in "Insert Revizyonlarının İçindeki Metni Yoksay" özelliğinin Word belgelerindeki ekleme revizyonlarını işlemek için nasıl kullanılacağını öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

Bu makalede, Aspose.Words for .NET kitaplığındaki Revizyonların İçindeki Metni Yoksay işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, belgeleri işlerken ekleme revizyonlarının içindeki metni yok saymak istediğimizde kullanışlıdır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yeni Belge Oluşturma

 İnsert revizyonlarının içindeki metni manipüle etmeye başlamadan önce, Aspose.Words for .NET kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
Document doc = new Document();
```

## 2. Adım: Revizyon takibi ile metin ekleyin

 Bir belgemiz olduğunda, revizyon izlemeli bir metin ekleyebiliriz.`DocumentBuilder` nesne. Örneğin, revizyon takibi ile "Eklendi" metnini eklemek için`StartTrackRevisions`, `Writeln` Ve`StopTrackRevisions` yöntemler:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## 3. Adım: İncelenmemiş metni ekleyin

 Revizyon izlemeli metne ek olarak,`DocumentBuilder`nesne. Örneğin, "Metin" metnini düzeltme yapmadan eklemek için`Write` yöntem:

```csharp
builder.Write("Text");
```

## 4. Adım: Revizyonların İçindeki Metni Yoksay işlevinin kullanılması

 Sonraki işlemlerde ekleme revizyonları içindeki metni yok saymak için bir`FindReplaceOptions` nesne ve ayarlayın`IgnoreInserted` mülkiyet`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## 5. Adım: Arama ve değiştirme için normal ifadeleri kullanma

Belge metninde arama ve değiştirme işlemlerini gerçekleştirmek için düzenli ifadeler kullanacağız. Örneğimizde, "e" harfinin geçtiği tüm yerleri arayacağız ve bunları bir yıldız işaretiyle değiştireceğiz "* ".NET'leri kullanacağız`Regex` Bunun için sınıf:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## 6. Adım: Değiştirilmiş Belge Çıktısını Görüntüleme

Ara ve değiştir işlemini uyguladıktan sonra, belgenin değişen içeriğini kullanarak görüntüleyebiliriz.`GetText` yöntem:

```csharp
Console.WriteLine(doc.GetText());
```

## Adım 7: Ekleme Revizyonlarını Dahil Etmek İçin Seçenekleri Değiştirme

 İnsert revizyonlarının içindeki metni çıktı sonucuna dahil etmek istiyorsak, insert revizyonlarını göz ardı etmemek için seçenekleri değiştirebiliriz. Bunun için ayarlayacağımız`IgnoreInserted` mülkiyet`false`:

```csharp
options.IgnoreInserted = false;
```

## Adım 8: Değiştirilmiş Belgeyi Revizyon Ekleme ile Görüntüleme

Seçenekleri değiştirdikten sonra, eklenen revizyonların içindeki metinle sonucu elde etmek için aramayı gerçekleştirebilir ve tekrar değiştirebiliriz:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Aspose.Words for .NET kullanan Insert Revizyonları İçerisindeki Metni Yoksay için örnek kaynak kodu

Aspose.Words for .NET ile Revizyonlar İçerisindeki Metni Yoksay işlevinin kullanımını gösteren tam örnek kaynak kodunu burada bulabilirsiniz:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// İzleme revizyonları ile metin ekleyin.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Düzeltilmemiş metin ekleyin.
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

Bu makalede, Aspose.Words for .NET'te Revizyonların İçinde Metni Yoksay işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, revizyonları ve düzeltilmemiş metni izleyerek metin eklemek, Revizyonların İçindeki Metni Yoksay işlevini kullanmak, normal ifadelerle arama ve değiştirme işlemlerini gerçekleştirmek ve değiştirilen belgeyi görüntülemek için adım adım bir kılavuz izledik.