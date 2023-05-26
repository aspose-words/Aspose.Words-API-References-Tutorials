---
title: Maddeli liste
linktitle: Maddeli liste
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile madde işaretli liste oluşturmayı öğrenin Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/bulleted-list/
---

Bu eğitimde, size Aspose.Words for .NET ile madde işaretli liste oluşturmayı anlatacağız. Öğeleri numaralandırma kullanmadan listelemek için madde işaretli bir liste kullanılır.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Varsayılan Madde İşaretli Liste Uygulama

 Belge oluşturucuyu kullanarak varsayılan bir madde işaretli liste uygulayabiliriz.`ApplyBulletDefault` yöntem.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## 3. Adım: Madde İşareti Formatını Özelleştirme

 Özelliklerine erişerek madde işareti formatını özelleştirebiliriz.`ListFormat.List.ListLevels[0]`. Bu örnekte, "-" tiresini madde işareti olarak kullanıyoruz.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## 4. Adım: Listeye öğe ekleme

 Artık belge oluşturucuyu kullanarak madde işaretli listeye öğeler ekleyebiliriz.`Writeln` yöntem.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Adım 5: Girintiyi listeden kaldırma

 Bir alt liste oluşturmak istiyorsak, girintiyi kullanarak artırabiliriz.`ListFormat.ListIndent()` yöntem. Bu örnekte, 2a ve 2b maddelerine bir alt liste ekliyoruz.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Aspose.Words for .NET kullanan Madde İşaretli Liste için örnek kaynak kodu


```csharp
	// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
	DocumentBuilder builder = new DocumentBuilder();

	builder.ListFormat.ApplyBulletDefault();
	builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();

	builder.Writeln("Item 2a");
	builder.Writeln("Item 2b");
            
```

Tebrikler! Artık Aspose.Words for .NET ile madde işaretli liste oluşturmayı öğrendiniz.

