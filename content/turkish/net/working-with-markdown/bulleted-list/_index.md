---
title: Maddeli liste
linktitle: Maddeli liste
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile madde işaretli liste oluşturmayı öğrenin. Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/bulleted-list/
---

Bu eğitimde size Aspose.Words for .NET ile madde işaretli listenin nasıl oluşturulacağını anlatacağız. Madde işaretli liste, öğeleri numaralandırma kullanılmadan listelemek için kullanılır.

## 1. Adım: Belge oluşturucuyu kullanma

Öncelikle belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Adım 2: Varsayılan Madde İşaretli Liste Uygulama

 Belge oluşturucuyu kullanarak varsayılan madde işaretli listeyi uygulayabiliriz.`ApplyBulletDefault` yöntem.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## 3. Adım: Madde İşareti Formatını Özelleştirme

Özelliklerine erişerek madde işareti biçimini özelleştirebiliriz.`ListFormat.List.ListLevels[0]`. Bu örnekte, madde işareti olarak "-" çizgisini kullanıyoruz.

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

 Bir alt liste oluşturmak istiyorsak girintiyi aşağıdaki komutu kullanarak artırabiliriz:`ListFormat.ListIndent()` yöntem. Bu örnekte 2a ve 2b öğelerine bir alt liste ekliyoruz.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Aspose.Words for .NET kullanan Madde İşaretli Liste için örnek kaynak kodu


```csharp
// Belgeye içerik eklemek için belge oluşturucuyu kullanın.
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

### SSS'ler

#### S: Markdown'da madde işaretli liste nasıl oluşturulur?

C: Markdown'da madde işaretli bir liste oluşturmak için her liste öğesine bir madde işareti simgesiyle başlayın (`-`, `*` , veya`+`), ardından bir boşluk gelir.

#### S: Madde işaretli listeleri Markdown'da iç içe yerleştirebilir misiniz?

C: Evet, iç içe geçmiş her liste öğesinin önüne dört boşluk ekleyerek madde işaretli listeleri Markdown'da iç içe yerleştirmek mümkündür.

#### S: Madde işareti sembolleri nasıl özelleştirilir?

C: Standart Markdown'da madde işareti sembolleri önceden tanımlanmıştır. Ancak bazı Markdown düzenleyicileri, bunları belirli uzantıları kullanarak özelleştirmenize olanak tanır.

#### S: Markdown'daki madde işaretli listeler girintiyi destekliyor mu?

C: Evet, Markdown'daki madde işaretli listeler girintiyi destekler. Boşlukları veya sekmeleri kullanarak sola kaydırma ekleyebilirsiniz.

#### S: Liste öğelerine bağlantılar veya satır içi metin eklenebilir mi?

C: Evet, uygun Markdown sözdizimini kullanarak liste öğelerine bağlantılar veya satır içi metin ekleyebilirsiniz.
