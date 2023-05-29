---
title: İtalik Metin
linktitle: İtalik Metin
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET Adım adım kılavuz ile metni italik yapmayı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/italic-text/
---

Bu örnekte, italik metin özelliğini Aspose.Words for .NET ile nasıl kullanacağınız konusunda size yol göstereceğiz. İtalik metin, bir belgenin belirli bölümlerini vurgulamak için kullanılır.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Metni İtalik Yap

 Yazı tipini ayarlayarak metni italik hale getirebiliriz.`Italic` mülkiyet`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### Aspose.Words for .NET ile italik metin için örnek kaynak kodu


```csharp
// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// Metni italik yapın.
builder.Font.Italic = true;
builder.Writeln("This text will be Italic");
```

Tebrikler! Artık italik metin özelliğini Aspose.Words for .NET ile nasıl kullanacağınızı öğrendiniz.

