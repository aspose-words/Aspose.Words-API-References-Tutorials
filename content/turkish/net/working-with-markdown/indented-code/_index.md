---
title: Girintili Kod
linktitle: Girintili Kod
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile girintili kodun nasıl kullanılacağını öğrenin. Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/indented-code/
---

Bu örnekte girintili kod özelliğinin Aspose.Words for .NET ile nasıl kullanılacağını açıklayacağız. Girintili kod, belirli biçimlendirmeye sahip kod bloklarını görsel olarak temsil etmek için kullanılır.

## 1. Adım: Belge oluşturucuyu kullanma

Öncelikle belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Girintili kod için stil ekleyin

Girintili kod için özel bir stil ekleyeceğiz.`Styles.Add` yöntemi`Document` nesne. Bu örnekte girintili kod için "IndentedCode" adında bir stil oluşturuyoruz.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## 3. Adım: Girintili kodu ekleyin

Artık "IndentedCode" özel stilini kullanarak girintili bir kod bloğu ekleyebiliriz.

```csharp
builder.Writeln("This is an indented code block");
```

### Aspose.Words for .NET ile girintili kod için örnek kaynak kodu

```csharp
// Belgeye içerik eklemek için belge oluşturucuyu kullanın.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

Tebrikler! Artık Aspose.Words for .NET ile girintili kod özelliğini nasıl kullanacağınızı öğrendiniz.


### SSS'ler

#### S: Markdown'daki girintili kod nedir?

C: Markdown'daki girintili kod, Markdown belgesindeki kodu görüntülemek için kullanılan bir biçimlendirme yöntemidir. Her kod satırının boşluk veya sekmelerle girintilenmesinden oluşur.

#### S: Markdown'da girintili kod nasıl kullanılır?

C: Markdown'da girintili kod kullanmak için her kod satırını boşluk veya sekmelerle girintileyin.

#### S: Markdown'da girintili kodun avantajları nelerdir?

C: Markdown'daki girintili kod, kodun okunabilirliğini artırır ve okuyucuların anlamasını kolaylaştırır.

#### S: Markdown'daki girintili kod ile kod blokları arasındaki fark nedir?

C: Girintili kod, metne eklenen küçük kod parçacıkları için kullanılırken kod blokları, daha büyük kod parçalarını ayrı biçimlendirmede görüntülemek için kullanılır.

#### S: Markdown'daki girintili kod tüm Markdown düzenleyicileri tarafından destekleniyor mu?

C: Markdown'daki girintili kod desteği, Markdown editörleri arasında farklılık gösterebilir. Emin olmak için yayıncınızın özel belgelerini kontrol edin.