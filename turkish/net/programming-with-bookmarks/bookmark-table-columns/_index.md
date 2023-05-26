---
title: Yer İşareti Tablosu Sütunları
linktitle: Yer İşareti Tablosu Sütunları
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablo sütununa nasıl yer işareti koyacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/bookmark-table-columns/
---

Bu makalede, Aspose.Words for .NET kitaplığında Bookmark Table Columns işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, bir Word belgesindeki bir tablonun belirli bir sütununa yer işareti koymanıza ve o sütunun içeriğine erişmenize olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Tabloyu oluşturma

 Bir tablo sütununda yer imi oluşturmadan önce, tabloyu`DocumentBuilder` nesne. Örneğimizde iki satır ve iki sütun içeren bir tablo oluşturuyoruz:

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## 2. Adım: Sütun yer imini oluşturma

 biz kullanıyoruz`StartBookmark`tablonun belirli bir sütununda yer imi oluşturma yöntemi. Örneğimizde, yer imi için "Yer İşaretim" adını kullanıyoruz:

```csharp
builder. StartBookmark("MyBookmark");
```

## 3. Adım: Sütun içeriğine erişin

 Belgedeki tüm yer imlerini inceliyoruz ve adlarını gösteriyoruz. Yer imi bir sütunsa, sütun indeksini kullanarak o sütunun içeriğine erişiriz ve`GetText` yöntem:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### Aspose.Words for .NET kullanan Bookmark Table Columns için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir tablo sütununda yer imi oluşturmayı gösteren tam örnek kaynak kodu burada:

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Bookmark Table Columns işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir Word belgesindeki bir tablonun belirli bir sütununa yer işareti koymak ve o sütunun içeriğine atlamak için adım adım bir kılavuz izledik.