---
title: çitle çevrili kod
linktitle: çitle çevrili kod
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET Adım adım kılavuzla çitle çevrili kod özelliğinin nasıl kullanılacağını öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/fenced-code/
---

Bu örnekte, çitle çevrili kod özelliğini Aspose.Words for .NET ile nasıl kullanacağınız konusunda size yol göstereceğiz. çitle çevrili kod, belirli biçimlendirme ile kod bloklarını temsil etmek için kullanılır.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Korumalı kod için bir stil ekleme

 Şunu kullanarak çitle çevrili kod için özel bir stil ekleyeceğiz:`Styles.Add` yöntemi`Document` nesne. Bu örnekte, çitle çevrili kod için "FencedCode" adında bir stil oluşturuyoruz.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## 3. Adım: Bilgi olmadan çitle çevrili kod ekleme

Artık "FencedCode" özel stilini kullanarak herhangi bir bilgi dizisi içermeyen çitle çevrili bir kod bloğu ekleyebiliriz.

```csharp
builder.Writeln("This is an fenced code");
```

## 4. Adım: Bilgi dizesiyle çitle çevrili kod ekleyin

Başka bir özel stil kullanarak bir dizi bilgi içeren çitle çevrili bir kod bloğu da ekleyebiliriz. Bu örnekte, bir C# kod bloğunu temsil etmesi için "FencedCode.C#" adlı bir stil oluşturuyoruz.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Aspose.Words for .NET kullanan Fenced Code için örnek kaynak kodu

```csharp
// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```


