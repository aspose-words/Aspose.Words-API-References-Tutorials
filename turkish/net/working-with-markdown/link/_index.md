---
title: Bağlantı
linktitle: Bağlantı
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bağlantıları nasıl ekleyeceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/working-with-markdown/link/
---

Bu örnekte, bağlantılar özelliğini Aspose.Words for .NET ile nasıl kullanacağınız konusunda size yol göstereceğiz. Bağlantılar, web sitelerine veya diğer belgelere tıklanabilir referanslar oluşturmak için kullanılır.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Bağlantı ekleme

 kullanarak bir bağlantı ekleyebiliriz.`Insertlink` belge üreteci yöntemi. Burada "Aspose" olan bağlantı metnini ve hedef URL'yi belirtmemiz gerekiyor.

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com", yanlış);
```

### Aspose.Words for .NET ile bağlantılar için örnek kaynak kodu


```csharp
// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// Bağlantı ekle.
builder.Insertlink("Aspose", "https://www.aspose.com", yanlış);
```
Tebrikler! Artık bağlantılar özelliğini Aspose.Words for .NET ile nasıl kullanacağınızı öğrendiniz.

