---
title: Bağlantı Oluştur
linktitle: Bağlantı Oluştur
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesindeki TextBox'lar arasında nasıl bağlantı oluşturacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-textboxes/create-a-link/
---

## 1. Adım: Belgeyi ayarlama ve TextBox şekilleri oluşturma

 Başlamak için belgeyi kurmamız ve iki TextBox şekli oluşturmamız gerekiyor. Aşağıdaki kod, yeni bir örneğini başlatır.`Document` class ve iki metin kutusu şekli oluşturur:

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;
```

## Adım 2: Metin Kutuları arasında bir bağlantı oluşturma

 Şimdi kullanarak iki TextBox arasında bir bağlantı oluşturacağız.`IsValidLinkTarget()` yöntem ve`Next` ilk TextBox'ın özelliği.

```csharp
if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```

 bu`IsValidLinkTarget()` yöntem, ikinci TextBox'un birinci TextBox'un bağlantısı için geçerli bir hedef olup olamayacağını kontrol eder. Doğrulama başarılı olursa,`Next` ilk TextBox özelliği ikinci TextBox olarak ayarlanarak ikisi arasında bir bağlantı oluşturulur.

### Aspose.Words for .NET ile bağlantı kurmak için örnek kaynak kodu

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;

if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```