---
title: Yatay kural
linktitle: Yatay kural
second_title: Aspose.Words Belge İşleme API'sı
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


### SSS

#### S: Markdown'da nasıl yatay bir cetvel oluşturabilirim?

A: Markdown'da yatay bir cetvel oluşturmak için boş bir satırda aşağıdaki sembollerden birini kullanabilirsiniz: üç yıldız (\***), üç çizgi (\---) veya üç alt çizgi (\___).

#### S: Markdown'da yatay bir cetvelin görünümünü özelleştirebilir miyim?

C: Standart Markdown'da yatay cetvellerin görünümünü özelleştirmenin bir yolu yoktur. Ancak, bazı gelişmiş Markdown editörleri ve uzantıları ek özelleştirme özellikleri sunar.

#### S: Yatay cetveller tüm Markdown editörleri tarafından destekleniyor mu?

C: Evet, en popüler Markdown editörleri yatay cetvelleri destekler. Ancak, desteklendiğinden emin olmak için satıcınızın belgelerini kontrol etmek her zaman en iyisidir.

#### S: Markdown'da başka hangi öğeleri oluşturabilirim?

Y: Yatay cetvellere ek olarak, Markdown'da başlıklar, paragraflar, listeler, bağlantılar, resimler, tablolar ve daha fazlasını oluşturabilirsiniz.