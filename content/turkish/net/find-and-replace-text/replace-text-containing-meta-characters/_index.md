---
title: Kelime Meta Karakterler İçeren Metni Değiştir
linktitle: Kelime Meta Karakterler İçeren Metni Değiştir
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak Word belgelerinde meta karakterler içeren metni nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/replace-text-containing-meta-characters/
---
Bu makalede, Aspose.Words for .NET kütüphanesinde Meta Karakterler İçeren Metni Değiştir işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, belirli meta karakterleri içeren bir belgedeki metnin bölümlerini değiştirmenize olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## Adım 1: Yeni Bir Belge Oluşturma

 Meta karakter metin değişimini kullanmaya başlamadan önce Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2. Adım: Belgeye metin ekleyin

 Bir belgeye sahip olduğumuzda, bir kullanarak metin ekleyebiliriz.`DocumentBuilder` nesne. Örneğimizde, şunu kullanıyoruz:`Writeln` farklı bölümlere birden fazla paragraf metin ekleme yöntemi:

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

 Şimdi bulma ve değiştirme seçeneklerini bir kullanarak yapılandıracağız.`FindReplaceOptions` nesne. Örneğimizde değiştirilen paragrafların hizalamasını "Ortalanmış" olarak ayarladık:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## 4. Adım: Meta Karakterler İçeren Metni Değiştirme

 biz kullanıyoruz`Range.Replace`Meta karakterleri içeren metnin değiştirilmesini gerçekleştirme yöntemi. Örneğimizde, "bölüm" kelimesinin ve ardından paragraf sonu geçen her yeri aynı kelimeyle ve ardından birkaç tire ve yeni bir paragraf sonuyla değiştiriyoruz:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## 5. Adım: Özel metin etiketini değiştirme

 Biz de kullanıyoruz`Range.Replace` özel olanı değiştirme yöntemi "{insert-section}" bölüm sonu içeren metin etiketi. Örneğimizde şunu değiştiriyoruz "{insert-section}" bölüm sonu eklemek için "&b" ile:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## Adım 6: Düzenlenen belgeyi kaydetme

Son olarak değiştirilen belgeyi aşağıdaki komutu kullanarak belirtilen dizine kaydederiz:`Save` yöntem:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### Aspose.Words for .NET Kullanarak Meta Karakterler İçeren Metni Değiştirme için örnek kaynak kodu

Aspose.Words for .NET ile meta karakter içeren metin değiştirmenin kullanımını gösteren tam örnek kaynak kodunu burada bulabilirsiniz:

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

	// "Bölüm" sözcüğünden sonraki her paragraf sonunu ikiye katlayın, bir tür alt çizgi ekleyin ve ortalayın.
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// Özel metin etiketi yerine bölüm sonu ekleyin.
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Meta Karakterleri İçeren Metni Değiştir özelliğinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, metin eklemek, meta karakterleri içeren metni değiştirmek ve değiştirilen belgeyi kaydetmek için adım adım kılavuzu izledik.

### SSS'ler

#### S: Aspose.Words for .NET'teki Meta Karakterleri İçeren Metni Değiştir işlevi nedir?

C: Aspose.Words for .NET'teki Meta Karakterleri İçeren Metni Değiştir özelliği, bir belgede belirli meta karakterler içeren metin bölümlerini değiştirmenize olanak sağlar. Belgenizde meta karakterleri hesaba katarak gelişmiş değişiklikler yapmak için bu özelliği kullanabilirsiniz.

#### S: Aspose.Words for .NET'te yeni bir belge nasıl oluşturulur?

 C: Meta Karakterler İçeren Metni Değiştir işlevini kullanmadan önce Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmalısınız. Bu, bir örneği başlatarak yapılabilir.`Document` nesne. Yeni bir belge oluşturmak için örnek kod aşağıda verilmiştir:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### S: Aspose.Words for .NET kullanarak bir belgeye nasıl metin eklenir?

 C: Bir belgeye sahip olduğunuzda, bir metin ekleyebilirsiniz.`DocumentBuilder` nesne. Örneğimizde, şunu kullanıyoruz:`Writeln` farklı bölümlere birden fazla paragraf metin ekleme yöntemi:

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

 C: Şimdi bulma ve değiştirme seçeneklerini bir kullanarak yapılandıracağız.`FindReplaceOptions` nesne. Örneğimizde değiştirilen paragrafların hizalamasını "Ortalanmış" olarak ayarladık:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### S: Aspose.Words for .NET kullanarak bir belgede meta karakter içeren metin nasıl değiştirilir?

 C: Kullanıyoruz`Range.Replace` Meta karakterleri içeren metnin değiştirilmesini gerçekleştirme yöntemi. Örneğimizde, "bölüm" kelimesinin ve ardından paragraf sonu geçen her yeri aynı kelimeyle ve ardından birkaç tire ve yeni bir paragraf sonuyla değiştiriyoruz:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### S: Aspose.Words for .NET kullanarak bir belgede meta karakterler içeren özel bir metin etiketi nasıl değiştirilir?

 C: Biz de kullanıyoruz`Range.Replace` özel olanı değiştirme yöntemi "{insert-section}" bölüm sonu içeren metin etiketi. Örneğimizde şunu değiştiriyoruz "{insert-section}" bölüm sonu eklemek için "&b" ile:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### S: Düzenlenen belge Aspose.Words for .NET'te nasıl kaydedilir?

 C: Belgede değişiklik yaptıktan sonra, onu kullanarak belirtilen dizine kaydedebilirsiniz.`Save` yöntem:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```