---
title: Girintili Kod
linktitle: Girintili Kod
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile girintili kodu nasıl kullanacağınızı adım adım öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/indented-code/
---

Bu örnekte girintili kod özelliğinin Aspose.Words for .NET ile nasıl kullanılacağını açıklayacağız. Girintili kod, belirli biçimlendirme ile kod bloklarını görsel olarak temsil etmek için kullanılır.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Girintili kod için stil ekleyin

Girintili kod için özel bir stil ekleyeceğiz.`Styles.Add` yöntemi`Document` nesne. Bu örnekte, girintili kod için "IndentedCode" adlı bir stil oluşturuyoruz.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## 3. Adım: Girintili kod ekleyin

Artık "IndentedCode" özel stilini kullanarak girintili bir kod bloğu ekleyebiliriz.

```csharp
builder.Writeln("This is an indented code block");
```

### Aspose.Words for .NET ile girintili kod için örnek kaynak kodu

```csharp
// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

Tebrikler! Artık girintili kod özelliğinin Aspose.Words for .NET ile nasıl kullanılacağını öğrendiniz.


### SSS

#### S: Markdown'da girintili kod nedir?

Y: Markdown'da girintili kod, bir Markdown belgesinde kodu görüntülemek için kullanılan bir biçimlendirme yöntemidir. Her kod satırının boşluk veya sekmelerle girintilenmesinden oluşur.

#### S: Markdown'da girintili kod nasıl kullanılır?

A: Markdown'da girintili kod kullanmak için, her kod satırında boşluk veya sekme girintisi yapın.

#### S: Markdown'da girintili kodun avantajları nelerdir?

C: Markdown'daki girintili kod, kodun okunabilirliğini artırır ve okuyucuların anlamasını kolaylaştırır.

#### S: Markdown'da girintili kod ile kod blokları arasındaki fark nedir?

A: Girintili kod, metne eklenen küçük kod parçacıkları için kullanılırken, kod blokları daha büyük kod parçalarını ayrı biçimlendirmede görüntülemek için kullanılır.

#### S: Markdown'daki girintili kod, tüm Markdown editörleri tarafından destekleniyor mu?

C: Markdown'da girintili kod desteği, Markdown editörleri arasında değişiklik gösterebilir. Emin olmak için yayıncınızın özel belgelerini kontrol edin.