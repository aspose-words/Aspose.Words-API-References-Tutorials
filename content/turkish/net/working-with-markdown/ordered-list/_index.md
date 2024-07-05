---
title: Sıralı Liste
linktitle: Sıralı Liste
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile sıralı liste oluşturmayı öğrenin Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/ordered-list/
---

Bu örnekte Aspose.Words for .NET ile sıralı liste fonksiyonunun nasıl kullanılacağını açıklayacağız. Sıralı Liste, öğeleri sayılarla sırayla düzenlemenize olanak tanır.

## 1. Adım: Belge oluşturucuyu kullanma

Öncelikle yeni bir belge oluşturmak için belge oluşturucuyu kullanacağız.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Sıralı liste formatını uygulama

 Belge oluşturucuyu kullanarak sıralı liste formatını uygulayacağız.`ApplyBulletDefault`yöntem. Ayrıca liste seviyelerine gidip istediğimiz formatı ayarlayarak numaralandırma formatını da özelleştirebiliriz.

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

## 4. Adım: Listeye girinti ekleyin

 Belge oluşturucuyu kullanarak listeyi girintili hale getirebiliriz`ListIndent` yöntem.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Adım 5: Belgeyi kaydetme

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

Tebrikler! Artık Aspose.Words for .NET ile sıralı liste özelliğini nasıl kullanacağınızı öğrendiniz.


### SSS'ler

#### S: Markdown'da sıralı bir liste nasıl oluşturulur?

C: Markdown'da sıralı bir liste oluşturmak için her liste öğesine bir sayı ve ardından bir nokta (`1.`, `2.`, `3.`), ardından bir boşluk gelir.

#### S: Sıralı listeleri Markdown'da iç içe geçirebilir miyiz?

C: Evet, Markdown'da sıralı listeleri iç içe geçmiş her liste öğesinin önüne dört boşluk ekleyerek iç içe yerleştirmek mümkündür.

#### S: Sıralı listelerin numaralandırması nasıl özelleştirilir?

C: Standart Markdown'da sıralı liste numaralandırması otomatik olarak oluşturulur. Ancak bazı Markdown düzenleyicileri, belirli uzantıları kullanarak onu özelleştirmenize izin verir.

#### S: Markdown'daki sıralı listeler girintiyi destekliyor mu?

C: Evet, Markdown'daki sıralı listeler girintiyi destekler. Boşlukları veya sekmeleri kullanarak sola kaydırma ekleyebilirsiniz.

#### S: Liste öğelerine bağlantılar veya satır içi metin eklenebilir mi?

C: Evet, uygun Markdown sözdizimini kullanarak liste öğelerine bağlantılar veya satır içi metin ekleyebilirsiniz.