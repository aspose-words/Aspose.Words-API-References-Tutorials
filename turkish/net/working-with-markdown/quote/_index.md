---
title: Alıntı
linktitle: Alıntı
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile teklifin nasıl kullanılacağını öğrenin Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/quote/
---

Bu örnekte, alıntı özelliğinin Aspose ile nasıl kullanılacağını açıklayacağız. NET için Words Alıntı, metnin bölümlerini özel bir kenarlıkla çevreleyerek vurgulamak için kullanılır.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Varsayılan Alıntı Stilini Kullanma

Metne alıntı biçimlendirmesi uygulamak için "Alıntı" adlı varsayılan paragraf stilini kullanacağız.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## 3. Adım: Yuvalanmış düzeyler için stiller oluşturma

 Kullanarak iç içe seviyeler için stiller oluşturabiliriz.`Styles.Add` yöntemi`Document` nesne. Bu örnekte, iç içe bir alıntı düzeyini temsil etmek için "Alıntı1" adlı bir stil oluşturuyoruz.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Aspose.Words for .NET ile alıntılar için örnek kaynak kodu


```csharp
// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// Varsayılan olarak bir belge, birinci seviye için blok alıntı stilini saklar.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Stil devralma yoluyla iç içe düzeyler için stiller oluşturun.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

Tebrikler! Artık alıntı özelliğini Aspose.Words for .NET ile nasıl kullanacağınızı öğrendiniz.

