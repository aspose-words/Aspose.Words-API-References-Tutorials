---
title: Girintili Kod
linktitle: Girintili Kod
second_title: Aspose.Words for .NET API Referansı
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

