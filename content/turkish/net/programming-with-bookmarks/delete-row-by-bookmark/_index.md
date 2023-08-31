---
title: Word Belgesinde Yer İmine Göre Satırı Sil
linktitle: Word Belgesinde Yer İmine Göre Satırı Sil
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak word belgesindeki belirli bir yer imine dayalı bir tablo satırını nasıl sileceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/delete-row-by-bookmark/
---

Bu makalede, Aspose.Words for .NET kütüphanesinde Satırı Yer İmine Göre Sil fonksiyonunun nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, word belgesindeki belirli bir yer imine dayalı olarak bir tablo satırını silmenize olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yer işaretini alma

 biz kullanıyoruz`Bookmarks` Tablo satırını silmek için kullanmak istediğimiz belirli yer işaretini almak için belge aralığının özelliği:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Adım 2: Tablo satırını silme

 biz kullanıyoruz`GetAncestor` elde etmek için yöntem`Row` yer iminin ana öğesini yazın. Daha sonra şunu kullanırız:`Remove` tablo satırını kaldırma yöntemi:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Aspose.Words for .NET kullanarak Satırı Yer İmine Göre Silme için örnek kaynak kodu

Aspose.Words for .NET kullanarak belirli bir yer işaretine dayalı olarak bir tablo satırının silinmesini gösteren tam örnek kaynak kodu burada bulabilirsiniz:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Satırı Yer İmine Göre Sil fonksiyonunun nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belgedeki belirli bir yer imine dayalı olarak bir tablo satırını silmek için adım adım bir kılavuz izledik.

### Word belgesinde satırları yer imlerine göre silmek için SSS

#### S: Aynı yer işaretini kullanarak birden fazla satırı silebilir miyim?

C: Evet, aynı yer imini kullanarak birden fazla satırı silebilirsiniz. Ancak silinecek satır sayısını belirlemek ve sağlanan kod parçacığında gerekli ayarlamaları yapmak için kodunuzdaki mantığı işlemeniz gerekir.

#### S: Yer imi belgede mevcut değilse ne olur?

C: Belirtilen yer imi belgede mevcut değilse kod pasajı, yer imi nesnesi için boş bir değer döndürecektir. Bu nedenle, tablo satırını silmeyi denemeden önce uygun kontrolleri ekleyerek bu senaryoyu kodunuzda ele almanız gerekir.

#### S: Aspose.Words kütüphanesinin kullanımı ücretsiz mi?

 C: Aspose.Words kütüphanesi ticari bir kütüphanedir ve onu projelerinizde kullanmak için geçerli bir lisansa ihtiyacınız olabilir. Ziyaret edebilirsiniz[Aspose.Words for .NET API referansları](https://reference.aspose.com/words/net/) lisanslama seçenekleri ve fiyatları hakkında daha fazla bilgi edinmek için.

#### S: Word belgesinin belirli bir bölümündeki tablodaki satırları silebilir miyim?

C: Evet, bir Word belgesinin belirli bir bölümündeki tablodaki satırları silebilirsiniz. Belirli bir bölümü hedeflemek için sağlanan kod pasajını, söz konusu bölüm içindeki uygun aralığı veya yer işaretini kullanarak değiştirebilirsiniz.