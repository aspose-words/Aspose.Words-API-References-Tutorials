---
title: Alıntı
linktitle: Alıntı
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile teklifin nasıl kullanılacağını öğrenin Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/quote/
---

Bu örnekte Aspose ile alıntı özelliğinin nasıl kullanılacağını açıklayacağız. Words for .NET Alıntı, metin bölümlerini özel bir kenarlıkla çevreleyerek vurgulamak için kullanılır.

## 1. Adım: Belge oluşturucuyu kullanma

Öncelikle belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Adım 2: Varsayılan Alıntı Stilini Kullanma

Metne alıntı biçimlendirmesi uygulamak için "Alıntı" adı verilen varsayılan paragraf stilini kullanacağız.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## 3. Adım: İç içe düzeyler için stiller oluşturma

 kullanarak iç içe düzeyler için stiller oluşturabiliriz.`Styles.Add` yöntemi`Document`nesne. Bu örnekte, iç içe geçmiş bir teklif düzeyini temsil etmek için "Quote1" adında bir stil yaratıyoruz.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Aspose.Words for .NET ile alıntılar için örnek kaynak kodu


```csharp
// Belgeye içerik eklemek için belge oluşturucuyu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// Varsayılan olarak bir belge birinci düzey için blok alıntı stilini saklar.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Stil devralma yoluyla iç içe düzeyler için stiller oluşturun.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

Tebrikler! Artık Aspose.Words for .NET ile alıntı özelliğini nasıl kullanacağınızı öğrendiniz.


### SSS'ler

#### S: Markdown'da alıntı nedir?

C: Markdown'daki bir alıntı, diğer kaynaklardan alınan metin pasajlarını vurgulamanın veya ünlü alıntılara gönderme yapmanın bir yoludur.

#### S: Markdown'da tırnak işaretleri nasıl kullanılır?

C: Markdown'da bir alıntı kullanmak için alıntı metnini köşeli parantezlerin içine alın (`>`). Alıntıdaki her satır bir şeritle başlamalıdır.

#### S: Markdown tırnak işaretleri nitelikleri destekliyor mu?

C: Markdown alıntıları belirli nitelikleri desteklemez. Alıntılanan metnin formatıyla kolayca vurgulanırlar.

#### S: Markdown'a alıntılar ekleyebilir misiniz?

C: Evet, ekstra düzeyde açılı ayraçlar ekleyerek Markdown'da tırnak işaretlerini iç içe yerleştirmek mümkündür (`>`).