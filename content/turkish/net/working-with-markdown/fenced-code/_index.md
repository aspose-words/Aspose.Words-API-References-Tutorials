---
title: Çitle çevrili kod
linktitle: Çitle çevrili kod
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile çitlenmiş kod özelliğini nasıl kullanacağınızı öğrenin. Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/fenced-code/
---

Bu örnekte, Aspose.Words for .NET ile çitlenmiş kod özelliğinin nasıl kullanılacağı konusunda size yol göstereceğiz. çitle çevrilmiş kod, belirli biçimlendirmeye sahip kod bloklarını temsil etmek için kullanılır.

## 1. Adım: Belge oluşturucuyu kullanma

Öncelikle belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Sınırlandırılmış kod için stil ekleme

 Çitlerle çevrili kod için özel bir stil ekleyeceğiz.`Styles.Add` yöntemi`Document` nesne. Bu örnekte çitlenmiş kod için "FencedCode" adında bir stil oluşturuyoruz.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## 3. Adım: Bilgi olmadan çitle çevrili kod ekleme

Artık "FencedCode" özel stilini kullanarak hiçbir bilgi dizisi içermeyen çitlerle çevrili bir kod bloğu ekleyebiliriz.

```csharp
builder.Writeln("This is an fenced code");
```

## 4. Adım: Bilgi dizesiyle çitlerle çevrili kod ekleyin

Ayrıca başka bir özel stil kullanarak bir dizi bilgi içeren çitlerle çevrili bir kod bloğu da ekleyebiliriz. Bu örnekte, bir C# kod bloğunu temsil etmek için "FencedCode.C#" adlı bir stil yaratıyoruz.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Aspose.Words for .NET kullanan Korumalı Kod için örnek kaynak kodu

```csharp
// Belgeye içerik eklemek için belge oluşturucuyu kullanın.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### SSS'ler

#### S: Markdown'da sınırlandırılmış kod nedir?

C: Markdown'daki sınırlandırılmış kod, Markdown belgesindeki kodu görüntülemek için kullanılan bir biçimlendirme yöntemidir. Kodun belirli sınırlayıcılarla çerçevelenmesinden oluşur.

#### S: Markdown'da sınırlandırılmış kodun faydaları nelerdir?

C: Markdown'daki sınırlandırılmış kod, kodun okunabilirliğini artırır ve okuyucuların anlamasını kolaylaştırır. Ayrıca bazı Markdown düzenleyicilerinde sözdizimi vurgulamasının korunmasına da olanak tanır.

#### S: Markdown'da ayrılmış ve girintili kod arasındaki fark nedir?

C: Sınırlandırılmış kod, kodu çevrelemek için belirli sınırlayıcılar kullanır; girintili kod ise her kod satırının boşluk veya sekmelerle girintilenmesini içerir.

#### S: Markdown'daki sınırlandırılmış kod tüm Markdown editörleri tarafından destekleniyor mu?

C: Markdown'da sınırlandırılmış kod desteği, Markdown editörleri arasında farklılık gösterebilir. Emin olmak için yayıncınızın özel belgelerini kontrol edin.

