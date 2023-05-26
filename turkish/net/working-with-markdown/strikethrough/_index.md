---
title: Üstü çizili
linktitle: Üstü çizili
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET Adım adım kılavuz ile üzeri çizili metin stilini nasıl uygulayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/strikethrough/
---


Bu örnekte, üstü çizili metin stilini Aspose.Words for .NET kullanarak nasıl uygulayacağınızı size göstereceğiz. Üstü çizili metin, metnin silindiğini veya artık geçerli olmadığını belirtmek için kullanılır.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Üstü çizili metin stilini uygulayın

 Ayarlayarak üstü çizili metin stilini etkinleştireceğiz.`StrikeThrough` mülkiyeti`Font` itiraz etmek`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## 3. Adım: Üstü çizili metin ekleyin

 Artık belge oluşturucuyu kullanarak üstü çizili metin ekleyebiliriz.`Writeln` yöntem.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Aspose.Words for .NET ile üstü çizili metin için örnek kaynak kodu

```csharp
	// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
	DocumentBuilder builder = new DocumentBuilder();

	// Metni üstü çizili yapın.
	builder.Font.StrikeThrough = true;
	builder.Writeln("This text will be StrikeThrough");
            
```

Tebrikler! Artık üstü çizili metin stilini Aspose.Words for .NET ile nasıl uygulayacağınızı öğrendiniz.
