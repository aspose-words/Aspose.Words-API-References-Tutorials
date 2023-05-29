---
title: Masa
linktitle: Masa
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile tablo oluşturmayı öğrenin Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/table/
---


Bu örnekte, Aspose.Words for .NET kullanarak bir tablonun nasıl oluşturulacağını anlatacağız. Tablo, bilgileri satırlar ve sütunlar halinde düzenleyen bir veri yapısıdır.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## 2. Adım: Hücre ve veri ekleyin

 Kullanarak tablomuza hücreler ve veriler ekleyeceğiz.`InsertCell` yöntem ve`Writeln` belge üreteci yöntemi.

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### Aspose.Words for .NET ile bir tablo oluşturmak için örnek kaynak kodu

```csharp
// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// İlk satırı ekleyin.
builder.InsertCell();
builder.Writeln("a");
builder.InsertCell();
builder.Writeln("b");

// İkinci satırı ekleyin.
builder.InsertCell();
builder.Writeln("c");
builder.InsertCell();
builder.Writeln("d");
```

Tebrikler! Artık Aspose.Words for .NET ile tablo oluşturmayı öğrendiniz.
