---
title: Yatay kural
linktitle: Yatay kural
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile yatay bir kuralın nasıl ekleneceğini öğrenin. Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/horizontal-rule/
---

Bu örnekte size Aspose.Words for .NET ile yatay kural özelliğinin nasıl kullanılacağını göstereceğiz. Yatay Kural, bir belgenin bölümlerini görsel olarak ayırmak için kullanılır.

## 1. Adım: Belge oluşturucuyu kullanma

Öncelikle belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Adım 2: Yatay kural ekleme

 Aşağıdakileri kullanarak yatay bir kural ekleyebiliriz:`InsertHorizontalRule` belge oluşturucu yöntemi.

```csharp
builder. InsertHorizontalRule();
```

## Aspose.Words for .NET ile yatay kural için örnek kaynak kodu

```csharp
// Belgeye içerik eklemek için belge oluşturucuyu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// Yatay kural ekleyin.
builder.InsertHorizontalRule();
```

Tebrikler! Artık Aspose.Words for .NET'te yatay cetvel özelliğini nasıl kullanacağınızı öğrendiniz.


### SSS'ler

#### S: Markdown'da nasıl yatay cetvel oluşturabilirim?

C: Markdown'da yatay bir cetvel oluşturmak için boş bir satırda aşağıdaki sembollerden birini kullanabilirsiniz: üç yıldız işareti (\***), üç çizgi (\---) veya üç alt çizgi (\___).

#### S: Markdown'da yatay cetvelin görünümünü özelleştirebilir miyim?

C: Standart Markdown'da yatay cetvellerin görünümünü özelleştirmenin bir yolu yoktur. Ancak bazı gelişmiş Markdown düzenleyicileri ve uzantıları ek özelleştirme özellikleri sunar.

#### S: Yatay cetveller tüm Markdown editörleri tarafından destekleniyor mu?

C: Evet, çoğu popüler Markdown düzenleyicisi yatay cetvelleri destekler. Ancak desteklendiğinden emin olmak için satıcınızın belgelerini kontrol etmek her zaman en iyisidir.

#### S: Markdown'da başka hangi öğeleri oluşturabilirim?

C: Markdown'da yatay cetvellerin yanı sıra başlıklar, paragraflar, listeler, bağlantılar, resimler, tablolar ve daha fazlasını oluşturabilirsiniz.