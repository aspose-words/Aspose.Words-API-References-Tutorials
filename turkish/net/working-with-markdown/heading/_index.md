---
title: Başlık
linktitle: Başlık
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile başlığı nasıl kullanacağınızı adım adım öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/heading/
---

Bu örnekte, size başlıklar özelliğini Aspose.Words for .NET ile nasıl kullanacağınızı göstereceğiz. Başlıklar, bir belgenin içeriğini yapılandırmak ve öncelik sırasına koymak için kullanılır.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Başlık Stillerini Özelleştirme

Varsayılan olarak, Word'deki başlık stilleri kalın ve italik biçimlendirmeye sahip olabilir. Bu özelliklerin uygulanmasını istemiyorsak, onları açıkça "yanlış" olarak ayarlamamız gerekir.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## 3. Adım: 1. Düzey Başlık Ekleme

 Uygun paragraf stili adını belirleyerek ve`Writeln` başlığın içeriğini yazma yöntemi.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

### Aspose.Words for .NET ile başlık için örnek kaynak kodu


```csharp
// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// Word'deki Başlık stilleri varsayılan olarak Kalın ve İtalik biçimlendirmeye sahip olabilir.
//Vurgulanmak istemiyorsak, bu özellikleri açıkça false olarak ayarlayın.
builder.Font.Bold = false;
builder.Font.Italic = false;

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

Tebrikler! Artık başlıklar özelliğini Aspose.Words for .NET ile nasıl kullanacağınızı öğrendiniz.


