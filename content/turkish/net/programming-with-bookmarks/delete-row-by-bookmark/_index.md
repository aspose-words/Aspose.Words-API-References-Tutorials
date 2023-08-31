---
title: Word Belgesinde Yer İşaretine Göre Satırı Sil
linktitle: Word Belgesinde Yer İşaretine Göre Satırı Sil
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak word belgesindeki belirli bir yer imine dayalı bir tablo satırını nasıl sileceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/delete-row-by-bookmark/
---

Bu makalede, Aspose.Words for .NET kitaplığındaki Yer İşaretine Göre Satırı Sil işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, word belgesindeki belirli bir yer imine dayalı olarak bir tablo satırını silmenizi sağlar.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yer imini alma

 biz kullanıyoruz`Bookmarks` tablo satırını silmek için kullanmak istediğimiz belirli yer işaretini almak için belge aralığının özelliği:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## 2. Adım: Tablo satırının silinmesi

 biz kullanıyoruz`GetAncestor` almak için yöntem`Row` yer iminin üst öğesini yazın. Daha sonra,`Remove` tablo satırını kaldırma yöntemi:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Aspose.Words for .NET kullanarak Satırı Yer İmine Göre Sil için örnek kaynak kodu

Aspose.Words for .NET kullanarak belirli bir yer imine dayalı bir tablo satırını silmeyi gösteren tam örnek kaynak kodu burada:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Yer İşaretine Göre Satırı Sil işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Belgedeki belirli bir yer imine dayalı olarak bir tablo satırını silmek için adım adım ilerleyen bir kılavuz izledik.

### Word belgesinde yer imlerine göre satır silmek için SSS

#### S: Aynı yer işaretini kullanarak birden çok satırı silebilir miyim?

C: Evet, aynı yer işaretini kullanarak birden çok satırı silebilirsiniz. Ancak, silinecek satır sayısını belirlemek ve sağlanan kod parçacığında gerekli ayarlamaları yapmak için kodunuzdaki mantığı kullanmanız gerekir.

#### S: Yer imi belgede yoksa ne olur?

C: Belgede belirtilen yer imi yoksa, kod parçacığı yer imi nesnesi için boş bir değer döndürür. Bu nedenle, tablo satırını silmeye çalışmadan önce uygun kontrolleri ekleyerek bu senaryoyu kodunuzda işlemeniz gerekir.

#### S: Aspose.Words kitaplığının kullanımı ücretsiz mi?

 Y: Aspose.Words kitaplığı ticari bir kitaplıktır ve onu projelerinizde kullanmak için geçerli bir lisansa ihtiyacınız olabilir. ziyaret edebilirsiniz[Aspose.Words for .NET API referansları](https://reference.aspose.com/words/net/) lisanslama seçenekleri ve fiyatlandırma hakkında daha fazla bilgi edinmek için.

#### S: Word belgesinin belirli bir bölümündeki bir tablodan satırları silebilir miyim?

C: Evet, bir Word belgesinin belirli bir bölümündeki bir tablodan satırları silebilirsiniz. Belirli bir bölümü hedeflemek için sağlanan kod parçacığını, o bölümdeki uygun aralığı veya yer işaretini kullanarak değiştirebilirsiniz.