---
title: İçerideki Metni Yoksay Revizyonları Sil
linktitle: İçerideki Metni Yoksay Revizyonları Sil
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'in "Düzeltmelerin İçindeki Metni Yoksay, Düzeltmeleri Yoksay" özelliğini nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

Bu makalede, Aspose.Words for .NET kütüphanesindeki "İçerdeki Metni Silme Düzeltmelerini Yoksay" özelliğinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, belgelerle Kelime İşleme sırasında silme revizyonlarının içindeki metni göz ardı etmek istediğimizde kullanışlıdır.

## Aspose.Words for .NET kütüphanesine genel bakış

Kod detaylarına girmeden önce Aspose.Words for .NET kütüphanesini kısaca tanıtayım. .NET uygulamalarında Word belgelerinin oluşturulmasına, değiştirilmesine ve dönüştürülmesine olanak tanıyan güçlü bir kütüphanedir. Revizyon yönetimi de dahil olmak üzere belgelerle Kelime İşleme için birçok gelişmiş özellik sunar.

## "Düzeltmelerin İçindeki Metni Yoksay Silme" özelliğini anlama

Aspose.Words for .NET'teki "Silme Düzeltmelerinin İçindeki Metni Yoksay" özelliği, metni bulma ve değiştirme gibi belirli işlemler sırasında revizyon silme içindeki metnin göz ardı edilip edilmeyeceğini belirlemenize olanak tanır. Bu özellik etkinleştirildiğinde, revizyonların içindeki silinen metinler işlemler sırasında dikkate alınmaz.

## Adım 1: Aspose.Words for .NET kullanarak yeni bir belge oluşturma

 Bir belgedeki metni değiştirmeye başlamadan önce Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
Document doc = new Document();
```

## Adım 2: Düzeltilmemiş metni belgeye ekleme

 Bir belgeye sahip olduğumuzda, incelenmemiş metni bir`DocumentBuilder` nesne. Örneğin, "Silinmiş Metin" metnini eklemek için şunu kullanabiliriz:`Writeln` Ve`Write` yöntemler:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## 3. Adım: Düzeltmeleri takip ederek bir paragrafı kaldırma

"Revizyonları Sil İçerdeki Metni Yoksay" özelliğinin kullanımını göstermek için, revizyon izlemeyi kullanarak belgeden bir paragrafı sileceğiz. Bu, bu özelliğin sonraki işlemleri nasıl etkilediğini görmemizi sağlayacaktır.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## 4. Adım: "Düzeltmelerin İçindeki Metni Yoksay Silme" özelliğini uygulama

 Artık bir paragrafı silerek belgemizi hazırladığımıza göre, "İçerdeki Metni Sil Revizyonları Yoksay" özelliğini kullanarak etkinleştirebiliriz.`FindReplaceOptions` nesne. biz ayarlayacağız`IgnoreDeleted`mülkiyet`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## 5. Adım: Bul ve değiştir için normal ifadeleri kullanma

Belge metni üzerinde arama ve değiştirme işlemlerini gerçekleştirmek için normal ifadeleri kullanacağız. Örneğimizde "e" harfinin geçtiği tüm yerleri arayacağız ve bunları yıldız işaretiyle değiştireceğiz "* ". .AÇIK`Regex` Bunun için sınıf kullanılır:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Adım 6: Değiştirilen belge çıktısının görüntülenmesi

 Arama ve değiştirmeyi uyguladıktan sonra, belgenin değişen içeriğini aşağıdaki komutu kullanarak görüntüleyebiliriz:`GetText` yöntem:

```csharp
Console.WriteLine(doc.GetText());
```

## 7. Adım: Silinen metni içerecek şekilde seçenekleri değiştirme

 Silinen metni çıktı sonucuna dahil etmek istiyorsak, seçenekleri silinen metni göz ardı etmeyecek şekilde değiştirebiliriz. Bunun için ayarlayacağız`IgnoreDeleted`mülkiyet`false`:

```csharp
options. IgnoreDeleted = false;
```

## Adım 8: Değiştirilen belgenin silinmiş metinle çıktısının alınması

Seçenekleri değiştirdikten sonra, aramayı gerçekleştirebilir ve silinen metnin dahil olduğu sonucu elde etmek için tekrar değiştirebiliriz:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Aspose.Words for .NET kullanarak İçerdeki Metni Yoksay Revizyonları Silme için örnek kaynak kodu

Aspose.Words for .NET ile "İçerdeki Metni Silme Düzeltmelerini Yoksay" özelliğinin kullanımını gösteren tam örnek kaynak kodunu burada bulabilirsiniz:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Düzeltilmemiş metni ekleyin.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Düzeltmeleri takip ederek ilk paragrafı kaldırın.
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

Bu makalede, Aspose.Words for .NET'te "İçerdeki Metni Silme Düzeltmelerini Yoksay" özelliğinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bu özellik, belgeleri düzenlerken silme revizyonlarının içindeki metni göz ardı etmek için kullanışlıdır. Bir belge oluşturmak, metin eklemek, revizyon takibi ile bir paragrafı silmek, "Revizyonları Silme İçindeki Metni Yoksay" özelliğini uygulamak ve bul ve değiştir işlemlerini gerçekleştirmek için adım adım bir kılavuz izledik.

### SSS'ler

#### S: Aspose.Words for .NET'teki "Revizyonları Sil İçerdeki Metni Yoksay" işlevi nedir?

C: Aspose.Words for .NET'teki "Silme Düzeltmelerinin İçindeki Metni Yoksay" işlevi, metin bulma ve değiştirme gibi belirli işlemler sırasında revizyon silme içindeki metnin göz ardı edilip edilmeyeceğini belirlemenize olanak tanır. Bu özellik etkinleştirildiğinde, revizyonların içindeki silinen metinler işlemler sırasında dikkate alınmaz.

#### S: Aspose.Words for .NET nedir?

C: Aspose.Words for .NET, Word belgelerini oluşturmak, düzenlemek ve .NET uygulamalarına dönüştürmek için kullanılan güçlü bir kütüphanedir. Revizyon yönetimi de dahil olmak üzere belgelerle Kelime İşleme için birçok gelişmiş özellik sunar.

#### S: Aspose.Words for .NET'te yeni bir belge nasıl oluşturulur?

 C: Bir belgedeki metni değiştirmeye başlamadan önce Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmanız gerekir. Bu, bir örneği başlatarak yapılabilir.`Document` nesne. Yeni bir belge oluşturmak için örnek kod aşağıda verilmiştir:

```csharp
Document doc = new Document();
```

#### S: Aspose.Words for .NET kullanarak bir belgeye düzenlenmemiş metin nasıl eklenir?

 C: Bir belgeye sahip olduğunuzda, incelenmemiş metni bir`DocumentBuilder` nesne. Örneğin, "Silinmiş Metin" metnini eklemek için`Writeln` Ve`Write` yöntemler:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### S: Aspose.Words for .NET'te revizyon izlemeli bir paragrafı nasıl silebilirim?

C: "Revizyonları Sil İçerdeki Metni Yoksay" işlevinin kullanımını göstermek için, revizyon izlemeyi kullanarak belgeden bir paragrafı sileceğiz. Bu, bu fonksiyonun sonraki işlemleri nasıl etkilediğini görmemizi sağlayacaktır.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### S: Aspose.Words for .NET'te "Revizyonların İçindeki Metni Yoksay, Düzeltmeleri Yoksay" özelliği nasıl etkinleştirilir?

 C: Artık belgemizi bir paragrafı silerek hazırladığımıza göre, "İçerdeki Metni Düzeltmeleri Silmede Yoksay" özelliğini kullanarak etkinleştirebiliriz.`FindReplaceOptions` nesne. biz ayarlayacağız`IgnoreDeleted`mülkiyet`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### S: Aspose.Words for .NET'te normal ifadeler kullanılarak nasıl arama ve değiştirme yapılır?

C: Belgenin metninde arama ve değiştirme işlemlerini gerçekleştirmek için normal ifadeleri kullanacağız. Örneğimizde "e" harfinin geçtiği tüm yerleri arayacağız ve bunları yıldız işaretiyle değiştireceğiz "* ". .NET'i kullanacağız`Regex` bunun için sınıf:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### S: Aspose.Words for .NET'te değişen belge içeriği nasıl görüntülenir?

C: Arama ve değiştirmeyi uyguladıktan sonra, belgenin değişen içeriğini şu düğmeyi kullanarak görüntüleyebiliriz:`GetText` yöntem:

```csharp
Console.WriteLine(doc.GetText());
```

#### S: Silinen metni Aspose.Words for .NET'te çıktı sonucuna nasıl dahil edebilirim?

 C: Silinen metni çıktı sonucuna dahil etmek istiyorsak, seçenekleri silinen metni göz ardı etmeyecek şekilde değiştirebiliriz. Bunun için ayarlayacağız`IgnoreDeleted`mülkiyet`false`:

```csharp
options. IgnoreDeleted = false;
```

#### S: Aspose.Words for .NET'te metni silinmiş olan düzenlenmiş belge nasıl gösterilir?

C: Seçenekleri değiştirdikten sonra, yeni bir arama yapabilir ve sonucu silinen metnin dahil olduğu şekilde elde etmek için değiştirebiliriz:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
