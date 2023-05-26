---
title: Satır Yer İşaretlerini Çöz
linktitle: Satır Yer İşaretlerini Çöz
second_title: Aspose.Words for .NET API Referansı
description: Diğer yer işaretlerini etkilemeden belirli satırları kaldırmak için iç içe satır yer işaretlerini nasıl çözeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/untangle-row-bookmarks/
---

Bu makalede, Aspose.Words for .NET kitaplığında Untangle Row Bookmarks işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu işlev, satırların yer imlerinin sonlarını yer imlerinin başlangıçlarıyla aynı satıra koymayı mümkün kılar.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Belgeyi yükleme

 biz kullanıyoruz`Document` varolan belgeyi bir dosyadan yüklemek için sınıf:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## 2. Adım: Satır Yer İşaretlerini Çözün

 biz kullanıyoruz`Untangle` yer imlerini satırlardan çözme işlevi. Bu işlev, satırların yer imi sonlarını yer imi başladığında aynı satıra koyma özel görevini gerçekleştirir:

```csharp
Untangle(doc);
```

## 3. Adım: Yer imine göre satırı silin

 biz kullanıyoruz`DeleteRowByBookmark` belirli bir satırı yer işaretine göre silme işlevi:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## 4. Adım: Diğer yer imlerinin bütünlüğünü kontrol edin

Yer iminin sonunun hala mevcut olup olmadığını kontrol ederek diğer yer imlerinin zarar görmediğini doğrularız:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Aspose.Words for .NET kullanan Untangle Row Bookmarks için örnek kaynak kodu**

Aspose.Words for .NET kullanarak yer imlerini satırlardan çözmek için tam örnek kaynak kodunu burada bulabilirsiniz:


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Bu, satır yer imi uçlarını yer imi başlangıçlarıyla aynı satıra yerleştirme özel görevini gerçekleştirir.
	Untangle(doc);

	// Artık diğer satırların yer imlerine zarar vermeden bir yer imi ile satırları kolayca silebiliriz.
	DeleteRowByBookmark(doc, "ROW2");

	// Bu sadece diğer yer iminin hasar görüp görmediğini kontrol etmek içindir.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Untangle Row Bookmarks özelliğinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Satır yer imlerini çözmek ve diğer yer imlerine zarar vermeden belirli bir satırı silmek için adım adım bir kılavuz izledik.