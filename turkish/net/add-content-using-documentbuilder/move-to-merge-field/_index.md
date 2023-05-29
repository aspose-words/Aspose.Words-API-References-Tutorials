---
title: Alanı Birleştirmek İçin Taşı
linktitle: Alanı Birleştirmek İçin Taşı
second_title: Aspose.Words for .NET API Referansı
description: Adım adım kılavuz kullanarak Aspose.Words for .NET'te Birleştirme Alanına Taşı özelliğini nasıl uygulayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/move-to-merge-field/
---

Bu örnekte, Aspose.Words for .NET'in Birleştirme Alanına Taşı özelliğini inceleyeceğiz. Aspose.Words, geliştiricilerin Word belgelerini program aracılığıyla oluşturmasına, değiştirmesine ve dönüştürmesine olanak sağlayan güçlü bir belge işleme kitaplığıdır. Birleştirme Alanına Taşı özelliği, bir belgedeki alanları birleştirmek için gezinmemize ve bunlar üzerinde çeşitli işlemler gerçekleştirmemize olanak tanır.


## Kaynak kodunu adım adım açıklama

Aspose.Words for .NET kullanarak Birleştirme Alanına Taşı özelliğinin nasıl kullanılacağını anlamak için kaynak kodunu adım adım inceleyelim.

## 1. Adım: Belge ve belge oluşturucuyu başlatma

Önce Document ve DocumentBuilder nesnelerini başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım Bir birleştirme alanı ekleme ve ardından metin ekleme

Bir birleştirme alanı eklemek için DocumentBuilder sınıfının InsertField yöntemini kullanın ve ardından bundan sonra metin ekleyin:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Adım 3: Oluşturucunun imleci şu anda belgenin sonundadır.

```csharp
Assert.Null(builder.CurrentNode);
```
## 4. Adım: Belge oluşturucu imlecini birleştirme alanına taşıma

Belge oluşturucu imlecini birleştirme alanına taşımak için DocumentBuilder sınıfının MoveToField yöntemini kullanın:

```csharp
builder.MoveToField(field, true);
```

## Birleştirme alanından hemen sonra metin ekleme

Belge oluşturucu imleci birleştirme alanının içine girdikten sonra, Write yöntemini kullanarak hemen arkasına metin ekleyebilirsiniz:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Aspose.Words for .NET kullanarak Birleştirme Alanına Taşı için örnek kaynak kodu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// DocumentBuilder'ı kullanarak bir alan ekleyin ve ardından bir dizi metin ekleyin.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// Oluşturucunun imleci şu anda belgenin sonundadır.
Assert.Null(builder.CurrentNode);
// İmleci alanın hemen sonrasına getirerek oluşturucuyu böyle bir alana taşıyabiliriz.
builder.MoveToField(field, true);

// İmlecin, alanın FieldEnd düğümünü geçen bir yerde olduğuna, yani aslında alanın içinde olmadığımıza dikkat edin.
// DocumentBuilder'ı bir alanın içine taşımak istersek,
// onu DocumentBuilder.MoveTo() yöntemini kullanarak bir alanın FieldStart veya FieldSeparator düğümüne taşımamız gerekecek.
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Çözüm

Aspose.Words for .NET'in Birleştirme Alanına Taşı özelliğini inceledik. DocumentBuilder sınıfını kullanarak bir belgedeki alanları birleştirmek için nasıl gezineceğimizi ve bunlar üzerinde işlemler yapmayı öğrendik. Bu özellik, birleştirme ile programlı olarak çalışırken kullanışlıdır.

