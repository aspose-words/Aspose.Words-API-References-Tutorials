---
title: çözmek
linktitle: çözmek
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bitişik tablo satırlarındaki iç içe yer imlerini nasıl çözeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/untangle/
---

Bu makalede, Aspose.Words for .NET kitaplığında Untangle işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu işlev, bitişik tablo satırlarında bulunan iç içe yer imlerini çözer.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Belge Yer İşaretlerine Göz Atın

Belgede bulunan tüm yer imleri arasında dolaşmak için bir foreach döngüsü kullanıyoruz:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Burada yer imlerini işlemek için kod
}
```

## 2. Adım: Yer işaretlerinden ana satırları alın

 biz kullanıyoruz`GetAncestor` yer iminin başlangıç ve bitiş düğümlerinin ana satırlarını alma yöntemleri:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## 3. Adım: İç İçe Yer İşaretlerini Çözün

Her iki ana satır da bulunursa ve yer imi bitişik satırlarda başlar ve biterse, yer işaretinin bitiş düğümünü üst satırdaki son hücrenin son paragrafının sonuna taşırız:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Aspose.Words for .NET kullanarak Untangle için örnek kaynak kodu

İşte Aspose.Words for .NET kullanarak iç içe yer imlerini çözmek için tam kaynak kodu örneği:

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// Hem yer imi hem de yer imi bitiş düğümünün ana satırını alın.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// Her iki satır da uygun bulunursa ve yer imi başlangıcı ve bitişi bitişik satırlarda yer alıyorsa,
		// yer imi bitiş düğümünü üst satırın son hücresindeki son paragrafın sonuna taşıyın.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Untangle işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bitişik tablo satırlarındaki iç içe yer imlerini çözmek için adım adım bir kılavuz izledik.