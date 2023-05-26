---
title: Yer İşaretine Göre Satırı Sil
linktitle: Yer İşaretine Göre Satırı Sil
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir belgedeki belirli bir yer imine dayalı bir tablo satırını nasıl sileceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/delete-row-by-bookmark/
---

Bu makalede, Aspose.Words for .NET kitaplığındaki Yer İşaretine Göre Satırı Sil işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, bir belgedeki belirli bir yer imine dayalı olarak bir tablo satırını silmenizi sağlar.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yer imini alma

 biz kullanıyoruz`Bookmarks`tablo satırını silmek için kullanmak istediğimiz belirli yer işaretini almak için belge aralığının özelliği:

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