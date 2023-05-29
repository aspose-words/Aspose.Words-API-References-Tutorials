---
title: Sıralı Liste
linktitle: Sıralı Liste
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile sıralı liste oluşturmayı öğrenin Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/ordered-list/
---

Bu örnekte, sıralı liste işlevinin Aspose.Words for .NET ile nasıl kullanılacağını açıklayacağız. Sıralı Liste, öğeleri sıralı olarak numaralarla düzenlemenizi sağlar.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, yeni bir belge oluşturmak için bir belge oluşturucu kullanacağız.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Sıralı liste biçimini uygulama

Belge oluşturucuyu kullanarak sıralı liste biçimini uygulayacağız.`ApplyBulletDefault` yöntem. Ayrıca liste seviyelerine gidip istediğimiz formatı ayarlayarak numaralandırma formatını özelleştirebiliriz.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## 3. Adım: Listeye öğe ekleme

 Belge oluşturucuyu kullanarak listeye öğeler ekleyebiliriz.`Writeln` yöntem.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## 4. Adım: Listeyi girintilendirin

 Belge oluşturucuyu kullanarak listeyi girintilendirebiliriz.`ListIndent` yöntem.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## 5. Adım: Belgeyi kaydetme

Son olarak belgeyi istediğimiz formatta kaydedebiliriz.

### Aspose.Words for .NET ile sıralı liste için örnek kaynak kodu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Tebrikler! Artık sıralı liste özelliğini Aspose.Words for .NET ile nasıl kullanacağınızı öğrendiniz.

