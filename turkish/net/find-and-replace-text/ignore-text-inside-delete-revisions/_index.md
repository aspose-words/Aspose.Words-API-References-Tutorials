---
title: İçindeki Metni Yoksay Düzeltmeleri Sil
linktitle: İçindeki Metni Yoksay Düzeltmeleri Sil
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'in "İçindeki Metni Yoksay Revizyonları Sil" özelliğini nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

Bu makalede, Aspose.Words for .NET kitaplığındaki "İçerideki Metni Yoksay, Düzeltmeleri Sil" özelliğinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, belgelerle çalışırken silme revizyonlarındaki metni yok saymak istediğimizde kullanışlıdır.

## Aspose.Words for .NET kitaplığına genel bakış

Kod detaylarına geçmeden önce Aspose.Words for .NET kütüphanesini kısaca tanıtmama izin verin. .NET uygulamalarında Word belgeleri oluşturmaya, değiştirmeye ve dönüştürmeye olanak sağlayan güçlü bir kitaplıktır. Revizyon yönetimi de dahil olmak üzere belgelerle çalışmak için birçok gelişmiş özellik sunar.

## "İçindeki Metni Yoksay, Düzeltmeleri Sil" özelliğini anlama

Aspose.Words for .NET'teki "Revizyonların İçindeki Metni Yoksay" özelliği, metin bulma ve değiştirme gibi belirli işlemler sırasında silme revizyonlarının içindeki metnin göz ardı edilip edilmeyeceğini belirlemenizi sağlar. Bu özellik etkinleştirildiğinde, revizyonların içindeki silinen metinler işlemler sırasında dikkate alınmaz.

## 1. Adım: Aspose.Words for .NET kullanarak yeni bir belge oluşturma

 Bir belgedeki metni değiştirmeye başlamadan önce Aspose.Words for .NET kullanarak yeni bir belge oluşturmamız gerekiyor. Bir örneğini oluşturarak yapılabilir`Document` nesne:

```csharp
Document doc = new Document();
```

## 2. Adım: Düzeltilmemiş metni belgeye ekleme

 Bir belgemiz olduğunda, incelenmemiş metni bir a kullanarak ekleyebiliriz.`DocumentBuilder` nesne. Örneğin, "Silinmiş Metin" metnini eklemek için şunu kullanabiliriz:`Writeln` Ve`Write` yöntemler:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## 3. Adım: Düzeltmeleri izleyerek bir paragrafı kaldırma

"Revizyonların İçindeki Metni Yoksay Sil" özelliğinin kullanımını göstermek için, revizyon izlemeyi kullanarak belgeden bir paragraf sileceğiz. Bu, bu özelliğin sonraki işlemleri nasıl etkilediğini görmemizi sağlayacaktır.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Adım 4: "İçindeki Metni Yoksay Düzeltmeleri Sil" özelliğini uygulama

 Artık bir paragrafı silerek belgemizi hazırladığımıza göre, "Ignore Text Inside Delete Revizyonları" özelliğini bir paragraf silerek etkinleştirebiliriz.`FindReplaceOptions` nesne. biz ayarlayacağız`IgnoreDeleted` mülkiyet`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## 5. Adım: Bul ve değiştir için normal ifadeleri kullanma

Belge metni üzerinde arama ve değiştirme işlemlerini gerçekleştirmek için normal ifadeler kullanacağız. Örneğimizde, "e" harfinin geçtiği tüm yerleri arayacağız ve bunları bir yıldız işaretiyle değiştireceğiz "* ". .AÇIK`Regex` sınıf bunun için kullanılır:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Adım 6: Değiştirilen belge çıktısının görüntülenmesi

Ara ve değiştir işlemini uyguladıktan sonra, belgenin değişen içeriğini kullanarak görüntüleyebiliriz.`GetText` yöntem:

```csharp
Console.WriteLine(doc.GetText());
```

## 7. Adım: Silinmiş metni dahil etmek için seçenekleri değiştirme

 Çıktı sonucuna silinen metni dahil etmek istiyorsak, silinen metni yok saymamak için seçenekleri değiştirebiliriz. Bunun için ayarlayacağımız`IgnoreDeleted` mülkiyet`false`:

```csharp
options. IgnoreDeleted = false;
```

## Adım 8: Değiştirilen belgenin silinmiş metinle çıktısını alma

Seçenekleri değiştirdikten sonra, silinen metnin dahil olduğu sonucu almak için aramayı gerçekleştirebilir ve tekrar değiştirebiliriz:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Aspose.Words for .NET kullanan Revizyonları Sil İçerideki Metni Yoksay için örnek kaynak kodu

Aspose.Words for .NET ile "İçerideki Metni Yoksay, Revizyonları Sil" özelliğinin kullanımını gösteren tam örnek kaynak kodunu burada bulabilirsiniz:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Düzeltilmemiş metin ekleyin.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// İzleme revizyonları ile ilk paragrafı kaldırın.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## Çözüm

Bu makalede, Aspose.Words for .NET'te "İçerideki Metni Yoksay, Düzeltmeleri Sil" özelliğinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bu özellik, belgeleri işlerken silme revizyonlarının içindeki metni yok saymak için kullanışlıdır. Belge oluşturmak, metin eklemek, revizyon izleme ile paragraf silmek, "İçerideki Metni Yoksay Revizyonları Sil" özelliğini uygulamak, bul ve değiştir işlemlerini gerçekleştirmek için adım adım bir kılavuz izledik.

