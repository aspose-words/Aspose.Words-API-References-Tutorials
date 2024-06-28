---
title: Word Belgesindeki Satır Yer İmlerini Çözme
linktitle: Word Belgesindeki Satır Yer İmlerini Çözme
second_title: Aspose.Words Belge İşleme API'si
description: Diğer yer imlerini etkilemeden belirli satırları kaldırmak için word belgesindeki iç içe geçmiş satır yer imlerini nasıl çözeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/untangle-row-bookmarks/
---

Bu makalede, Aspose.Words for .NET kütüphanesinde Untangle Row Bookmarks fonksiyonunun nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu işlev, satırların yer imlerinin sonlarının, yer imlerinin başlangıçlarıyla aynı satıra yerleştirilmesini mümkün kılar.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Belgeyi yükleme

 biz kullanıyoruz`Document` Mevcut belgeyi bir dosyadan yüklemek için sınıf:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Adım 2: Satır Yer İmlerini Çözün

 biz kullanıyoruz`Untangle` yer imlerini satırlardan ayırma işlevi. Bu işlev, satırların yer imi uçlarını yer iminin başladığı satırla aynı satıra yerleştirme özel görevini gerçekleştirir:

```csharp
Untangle(doc);
```

## 3. Adım: Satırı yer imine göre silin

 biz kullanıyoruz`DeleteRowByBookmark` Belirli bir satırı yer imine göre silme işlevi:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## 4. Adım: Diğer yer işaretlerinin bütünlüğünü kontrol edin

Yer iminin sonunun hala mevcut olup olmadığını kontrol ederek diğer yer imlerinin hasar görmediğini doğrularız:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Aspose.Words for .NET kullanarak Satır Yer İmlerini Çözmek için örnek kaynak kodu

Aspose.Words for .NET kullanarak satırlardaki yer işaretlerini çözmek için tam örnek kaynak kodunu burada bulabilirsiniz:


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Bu, satır yer işareti uçlarını yer işareti başlangıçlarıyla aynı satıra yerleştirme özel görevini gerçekleştirir.
	Untangle(doc);

	// Artık başka herhangi bir satırın yer imlerine zarar vermeden bir yer imine göre satırları kolayca silebiliriz.
	DeleteRowByBookmark(doc, "ROW2");

	// Bu sadece diğer yer iminin hasar görüp görmediğini kontrol etmek içindir.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### Kaynak kodunu çözün
```csharp

private void Untangle(Document doc)
        {
            foreach (Bookmark bookmark in doc.Range.Bookmarks)
            {
                // Hem yer işaretinin hem de yer işareti bitiş düğümünün üst satırını alın.
                Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
                Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

                // Her iki satır da uygun bulunursa ve yer işaretinin başlangıcı ve bitişi bitişik satırlarda yer alıyorsa,
                // yer imi bitiş düğümünü üst satırın son hücresindeki son paragrafın sonuna taşıyın.
                if (row1 != null && row2 != null && row1.NextSibling == row2)
                    row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
            }
        }

```

#### SilRowByBookmark kaynak kodu
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## Çözüm

Bu makalede, Aspose.Words for .NET'in Satır Yer İmlerini Çöz özelliğinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Satır yer imlerini çözmek ve diğer yer imlerine zarar vermeden belirli bir satırı silmek için adım adım bir kılavuz izledik.

### Word belgesindeki satır yer işaretlerini çözmek için SSS

#### S: Satır Yer İmlerini Çözme yalnızca tablolardaki satır yer imleriyle mi çalışır?

C: Evet, Satır Yer İmlerini Çözme özelliği, tablolardaki satır yer imlerini çözmek için özel olarak tasarlanmıştır. Bu işlev, dizilerdeki satır yer işaretlerini işlemek ve yer işareti uçlarının yer işareti başlangıçlarıyla aynı satırda olmasını sağlamak için kullanılabilir.

#### S: Satır Yer İmlerini Çözme işlevi orijinal belgenin içeriğini değiştirir mi?

C: Evet, Satır yer imlerinin şifresini çözme işlevi, satır yer imlerinin uçlarını, yer imlerinin başlangıçlarıyla aynı satıra yerleştirecek şekilde hareket ettirerek orijinal belgeyi değiştirir. Bu özelliği uygulamadan önce belgenin yedek bir kopyasını kaydettiğinizden emin olun.

#### S: Word belgemdeki satır yer işaretlerini nasıl tanımlayabilirim?

C: Satır yer imleri genellikle tablolarda belirli bölümleri işaretlemek için kullanılır. Belgedeki yer imlerine göz atarak ve yer imlerinin tablo satırlarında olup olmadığını kontrol ederek satır yer imlerini tanımlayabilirsiniz.

#### S: Bitişik olmayan tablolardaki satır yer işaretlerini çözmek mümkün mü?

C: Bu makalede sunulan Satır Yer İmlerini Çöz işlevi, bitişik tablolardaki satır yer imlerini çözmek için tasarlanmıştır. Bitişik olmayan tablolardaki satır yer işaretlerini çözmek için belgenin yapısına bağlı olarak kodda ek ayarlamalar yapılması gerekebilir.

#### S: Çözüldükten sonra satır yer imleri üzerinde başka hangi işlemleri yapabilirim?

C: Satır yer imleri çözüldükten sonra, gerektiği gibi farklı manipülasyonlar gerçekleştirebilirsiniz. Bu, yer imli satırlara içerik eklenmesini, silinmesini veya düzenlenmesini içerebilir. Belgenin geri kalanında istenmeyen etkiler oluşmasını önlemek için satır yer imlerini dikkatli bir şekilde kullandığınızdan emin olun.