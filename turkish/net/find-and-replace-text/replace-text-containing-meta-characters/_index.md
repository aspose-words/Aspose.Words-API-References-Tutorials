---
title: Meta Karakterler İçeren Metni Değiştir
linktitle: Meta Karakterler İçeren Metni Değiştir
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerinde meta karakter içeren metinleri nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/replace-text-containing-meta-characters/
---

Bu makalede, Aspose.Words for .NET kitaplığında Meta Karakterler İçeren Metni Değiştir işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, belirli meta karakterleri içeren bir belgedeki metin bölümlerini değiştirmenize olanak tanır.

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

 Bir belgemiz olduğunda, bir metin kullanarak metin ekleyebiliriz.`DocumentBuilder` nesne. Örneğimizde,`Writeln`farklı bölümlere birden çok metin paragrafı ekleme yöntemi:

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
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment

.Center;
```

## 4. Adım: Meta Karakter İçeren Metni Değiştirme

 biz kullanıyoruz`Range.Replace` Meta karakterleri içeren metnin değiştirilmesini gerçekleştirme yöntemi. Örneğimizde, "bölüm" kelimesinin geçtiği her bir paragraf sonunu aynı kelimeyle, ardından birkaç tire ve yeni bir paragraf sonu ile değiştiriyoruz:

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

