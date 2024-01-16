---
title: Könyvjelző táblázat oszlopai Word dokumentumban
linktitle: Könyvjelző táblázat oszlopai Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan lehet egy táblázat oszlopát könyvjelzővel ellátni Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-bookmarks/bookmark-table-columns/
---

Ebben a cikkben megvizsgáljuk a fenti C# forráskódot, hogy megértsük, hogyan használhatjuk a Bookmark Table Columns funkciót az Aspose.Words for .NET könyvtárban. Ez a funkció lehetővé teszi, hogy egy Word-dokumentumban lévő táblázat egy adott oszlopát könyvjelzővel jelölje meg, és hozzáférjen az oszlop tartalmához.

## Előfeltételek

- C# nyelv alapismerete.
- .NET fejlesztői környezet telepített Aspose.Words könyvtárral.

## 1. lépés: A táblázat létrehozása

 Mielőtt könyvjelzőt hoznánk létre egy táblázatoszlopon, először létre kell hoznunk a táblázatot a segítségével`DocumentBuilder`tárgy. Példánkban két sorból és két oszlopból álló táblázatot hozunk létre:

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

## 2. lépés: Az oszlop könyvjelzőjének létrehozása

 Használjuk a`StartBookmark` módszer könyvjelző létrehozására a táblázat egy adott oszlopában. Példánkban a "Saját könyvjelző" nevet használjuk a könyvjelzőként:

```csharp
builder. StartBookmark("MyBookmark");
```

## 3. lépés: Nyissa meg az oszlop tartalmát

 Végignézzük a dokumentum összes könyvjelzőjét, és megjelenítjük a nevüket. Ha a könyvjelző egy oszlop, az oszlop tartalmát az oszlopindex és a`GetText` módszer:

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

### Példa forráskódra a Bookmark Table Columns-hoz az Aspose.Words for .NET használatával

Íme a teljes minta forráskód, amely bemutatja egy könyvjelző létrehozását egy táblázat oszlopában az Aspose.Words for .NET használatával:

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

## Következtetés

Ebben a cikkben megvizsgáltuk a C# forráskódot, hogy megértsük, hogyan használhatjuk az Aspose.Words for .NET Bookmark Table Columns funkcióját. Lépésről lépésre követve könyvjelzővel jelöljük meg egy táblázat egy adott oszlopát egy Word-dokumentumban, és ugorjunk az oszlop tartalmára.

### GYIK a Word dokumentum könyvjelzőtáblázatának oszlopaihoz

#### K: Mik az előfeltételek az Aspose.Words for .NET "Könyvjelzői táblázat oszlopaihoz" funkciójának használatához?

V: Az Aspose.Words for .NET "Könyvjelzői táblázatoszlopokhoz" funkciójának használatához alapszintű C# nyelvtudással kell rendelkeznie. Szüksége van egy .NET fejlesztői környezetre is, amelyen az Aspose.Words könyvtár telepítve van.

#### K: Hogyan hozhatunk létre oszlopokat tartalmazó táblázatot Word-dokumentumban az Aspose.Words for .NET használatával?

 V: Ha egy Word-dokumentumban oszlopokat tartalmazó táblázatot szeretne létrehozni az Aspose.Words for .NET használatával, használhat egy`DocumentBuilder` objektum cellák és tartalom beszúrásához a táblázatba. Itt van egy minta kód:

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### K: Hogyan lehet egy táblázat oszlopát könyvjelzővel ellátni az Aspose.Words for .NET használatával?

 V: Ha könyvjelzőt szeretne létrehozni egy táblázat oszlopában az Aspose.Words for .NET használatával, használja a`StartBookmark` módszere a`DocumentBuilder` objektumot a könyvjelző elindításához egy adott táblázatoszlopban. Itt van egy minta kód:

```csharp
builder.StartBookmark("MyBookmark");
```

#### K: Hogyan lehet elérni a táblázatoszlop tartalmát a könyvjelzőből az Aspose.Words for .NET használatával?

V: Ha az Aspose.Words for .NET segítségével hozzá szeretne férni egy táblázatoszlop tartalmához egy könyvjelzőből, végignézheti a dokumentum összes könyvjelzőjét, ellenőrizheti, hogy a könyvjelző oszlop-e, és az oszlopok indexével hozzáférhet a dokumentum tartalmához. azt az oszlopot. Itt van egy minta kód:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // Csinálj valamit a rovat tartalmával...
         }
     }
}
```

#### K: Van-e korlátozás az oszlopok számának, amelyeket egy oszlopkönyvjelzővel rendelkező táblázatban hozhatok létre?

V: Az Aspose.Words for .NET segítségével oszlopkönyvjelzőket tartalmazó táblázatban létrehozható oszlopok száma nincs korlátozva. A korlát elsősorban a rendszeren elérhető erőforrásoktól és a használt Word fájlformátum specifikációitól függ. Javasoljuk azonban, hogy ne hozzon létre túl sok oszlopot, mivel ez befolyásolhatja a végleges dokumentum teljesítményét és olvashatóságát.