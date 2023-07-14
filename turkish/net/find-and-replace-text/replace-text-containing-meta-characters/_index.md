---
title: Meta Karakterler İçeren Metin Değiştirme Kelimesi
linktitle: Meta Karakterler İçeren Metin Değiştirme Kelimesi
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak Word belgelerinde metakarakterler içeren metinleri nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/replace-text-containing-meta-characters/
---
Bu makalede, Aspose.Words for .NET kitaplığında Word Change Text Containing Meta Characters işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, belirli meta karakterleri içeren bir belgedeki metin bölümlerini değiştirmenize olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yeni Belge Oluşturma

 Meta karakter metin değiştirmeyi kullanmaya başlamadan önce Aspose.Words for .NET kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2. Adım: Belgeye metin ekleyin

 Bir belgemiz olduğunda, bir metin kullanarak metin ekleyebiliriz.`DocumentBuilder` nesne. Örneğimizde,`Writeln` farklı bölümlere birden çok metin paragrafı ekleme yöntemi:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder. Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

## 3. Adım: Bul ve Değiştir Seçeneklerini Yapılandırma

 Şimdi bul ve değiştir seçeneklerini bir a kullanarak yapılandıracağız.`FindReplaceOptions` nesne. Örneğimizde, değiştirilen paragrafların hizalamasını "Ortalanmış" olarak ayarladık:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## 4. Adım: Meta Karakter İçeren Metni Değiştirme

 biz kullanıyoruz`Range.Replace`Meta karakterleri içeren metnin değiştirilmesini gerçekleştirme yöntemi. Örneğimizde, "bölüm" kelimesinin geçtiği her bir paragraf sonunu aynı kelimeyle, ardından birkaç tire ve yeni bir paragraf sonu ile değiştiriyoruz:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## 5. Adım: Özel bir metin etiketini değiştirme

 biz de kullanıyoruz`Range.Replace` özel değiştirme yöntemi "{insert-section}" bölüm sonu içeren metin etiketi. Örneğimizde değiştiriyoruz "{insert-section}bir bölüm sonu eklemek için "&b" ile:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## 6. Adım: Düzenlenen belgeyi kaydetme

 Son olarak, değiştirilmiş belgeyi kullanarak belirtilen bir dizine kaydediyoruz.`Save` yöntem:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### Aspose.Words for .NET kullanarak Meta Karakterler İçeren Metni Değiştirmek için örnek kaynak kodu

Aspose.Words for .NET ile metakarakterler içeren metin değişiminin kullanımını gösteren tam örnek kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Font.Name = "Arial";
	builder.Writeln("First section");
	builder.Writeln("  1st paragraph");
	builder.Writeln("  2nd paragraph");
	builder.Writeln("{insert-section}");
	builder.Writeln("Second section");
	builder.Writeln("  1st paragraph");

	FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
	findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;

	// "Bölüm" kelimesinden sonra her paragraf sonunu ikiye katlayın, bir tür alt çizgi ekleyin ve ortalayın.
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// Özel metin etiketi yerine bölüm sonu ekleyin.
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Meta Karakterler İçeren Metni Değiştir özelliğinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, metin eklemek, meta karakterleri içeren metni değiştirmek ve değiştirilen belgeyi kaydetmek için adım adım bir kılavuz izledik.

### SSS

#### S: Aspose.Words for .NET'te Meta Karakterler İçeren Metni Değiştir işlevi nedir?

C: Aspose.Words for .NET'teki Meta Karakterleri İçeren Metni Değiştir özelliği, belirli meta karakterleri içeren bir belgedeki metin bölümlerini değiştirmenize olanak tanır. Bu özelliği, belgenizde meta karakterleri dikkate alarak gelişmiş değiştirmeler yapmak için kullanabilirsiniz.

#### S: Aspose.Words for .NET'te yeni bir belge nasıl oluşturulur?

 Y: Meta Karakterler İçeren Metni Değiştir işlevini kullanmadan önce Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmalısınız. Bu, bir örneği başlatarak yapılabilir.`Document` nesne. İşte yeni bir belge oluşturmak için örnek bir kod:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### S: Aspose.Words for .NET kullanarak bir belgeye nasıl metin eklenir?

 C: Bir belgeniz olduğunda, bir metin kullanarak metin ekleyebilirsiniz.`DocumentBuilder` nesne. Örneğimizde,`Writeln` farklı bölümlere birden çok metin paragrafı ekleme yöntemi:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder.Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

#### S: Aspose.Words for .NET'te arama ve değiştirme seçenekleri nasıl yapılandırılır?

 A: Şimdi bul ve değiştir seçeneklerini bir a kullanarak yapılandıracağız.`FindReplaceOptions` nesne. Örneğimizde, değiştirilen paragrafların hizalamasını "Ortalanmış" olarak ayarladık:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### S: Aspose.Words for .NET kullanan bir belgede meta karakter içeren metin nasıl değiştirilir?

 C: Kullanıyoruz`Range.Replace` Meta karakterleri içeren metnin değiştirilmesini gerçekleştirme yöntemi. Örneğimizde, "bölüm" kelimesinin geçtiği her bir paragraf sonunu aynı kelimeyle, ardından birkaç tire ve yeni bir paragraf sonu ile değiştiriyoruz:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### S: Aspose.Words for .NET kullanan bir belgede meta karakterler içeren özel bir metin etiketi nasıl değiştirilir?

 A: Biz de kullanıyoruz`Range.Replace` özel değiştirme yöntemi "{insert-section}" bölüm sonu içeren metin etiketi. Örneğimizde değiştiriyoruz "{insert-section}bir bölüm sonu eklemek için "&b" ile:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### S: Düzenlenen belge Aspose.Words for .NET'te nasıl kaydedilir?

 C: Belgede değişiklik yaptıktan sonra, belgeyi aşağıdakileri kullanarak belirli bir dizine kaydedebilirsiniz:`Save` yöntem:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```