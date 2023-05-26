---
title: Yatay kural
linktitle: Yatay kural
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile yatay bir kuralı nasıl ekleyeceğinizi adım adım öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/horizontal-rule/
---

Bu örnekte, yatay kural özelliğini Aspose.Words for .NET ile nasıl kullanacağınızı göstereceğiz. Yatay Kural, bir belgenin bölümlerini görsel olarak ayırmak için kullanılır.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Yatay bir kural ekleme

 kullanarak yatay bir kural ekleyebiliriz.`InsertHorizontalRule` belge üreteci yöntemi.

```csharp
builder. InsertHorizontalRule();
```

## Aspose.Words for .NET ile yatay kural için örnek kaynak kodu

```csharp
	// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
	DocumentBuilder builder = new DocumentBuilder();

	// Yatay kural ekleyin.
	builder.InsertHorizontalRule();
            
```

Tebrikler! Artık yatay kural özelliğini Aspose.Words for .NET ile nasıl kullanacağınızı öğrendiniz.


