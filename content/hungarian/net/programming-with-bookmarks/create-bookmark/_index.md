---
title: Hozzon létre könyvjelzőt a Word dokumentumban
linktitle: Hozzon létre könyvjelzőt a Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre könyvjelzőket Word-dokumentumban, és hogyan adhat meg könyvjelző-előnézeti szinteket PDF-ben az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-bookmarks/create-bookmark/
---

Ebben a cikkben megvizsgáljuk a fenti C# forráskódot, hogy megértsük, hogyan használható a Könyvjelző létrehozása funkció az Aspose.Words for .NET könyvtárban. Ez a funkció lehetővé teszi könyvjelzők létrehozását egy dokumentumban, és könyvjelző-előnézeti szintek megadását a kimeneti PDF-fájlban.

## Előfeltételek

- C# nyelv alapismerete.
- .NET fejlesztői környezet telepített Aspose.Words könyvtárral.

## 1. lépés: A dokumentum és a generátor létrehozása

 A könyvjelzők létrehozása előtt létre kell hoznunk egy dokumentumot és egy dokumentumkészítőt a`Document` és`DocumentBuilder` objektumok:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: A fő könyvjelző létrehozása

 Használjuk a`StartBookmark` módszer a fő könyvjelző elindításához és a`EndBookmark` módszer a megszüntetésére. Közben szöveget és egyéb könyvjelzőket is hozzáadhatunk:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Adjon hozzá további könyvjelzőket vagy szöveget.

builder. EndBookmark("My Bookmark");
```

## 3. lépés: Beágyazott könyvjelzők létrehozása

 A fő könyvjelzőn belül is létrehozhatunk beágyazott könyvjelzőket. Ugyanazt használjuk`StartBookmark` és`EndBookmark` módszerek a beágyazott könyvjelzők létrehozására és befejezésére:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## 4. lépés: Adja meg a könyvjelző előnézeti szintjét a kimeneti PDF-fájlban

 Használjuk a`PdfSaveOptions` objektumot a könyvjelző előnézeti szintjeinek megadásához a kimeneti PDF-fájlban. Használjuk a`BookmarksOutlineLevels` ingatlan

  fő könyvjelzők és beágyazott könyvjelzők hozzáadásához a megfelelő szintekkel:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Példa forráskódra a Könyvjelző létrehozása az Aspose.Words segítségével .NET-hez

Íme a teljes példaforráskód, amely bemutatja a könyvjelzők létrehozását az Aspose.Words for .NET használatával:

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## Következtetés

Ebben a cikkben megvizsgáltuk a C# forráskódot, hogy megértsük, hogyan használható az Aspose.Words for .NET Könyvjelző létrehozása funkciója. Követtünk egy lépésről lépésre szóló útmutatót a könyvjelzők dokumentumban történő létrehozásához és a könyvjelző előnézeti szintjének megadásához a kimeneti PDF-fájlban.

### GYIK

#### K: Mik az előfeltételek az Aspose.Words for .NET "Könyvjelzők létrehozása" funkciójának használatához?

V: Az Aspose.Words for .NET "Könyvjelzők létrehozása" funkciójának használatához alapszintű C# nyelvtudással kell rendelkeznie. Szüksége van egy .NET fejlesztői környezetre is, amelyen az Aspose.Words könyvtár telepítve van.

#### K: Hogyan lehet dokumentumot létrehozni az Aspose.Words for .NET-ben?

 V: Dokumentum létrehozásához az Aspose.Words for .NET programban használhatja a`Document` osztály. Itt van egy minta kód:

```csharp
Document doc = new Document();
```

#### K: Hogyan lehet főkönyvjelzőt létrehozni egy dokumentumban az Aspose.Words for .NET használatával?

 V: Ha egy dokumentumban fő könyvjelzőt szeretne létrehozni az Aspose.Words for .NET használatával, használja a`StartBookmark` módszerrel indítsa el a könyvjelzőt, adjon hozzá szöveget vagy más könyvjelzőket, majd használja a` EndBookmark` hogy vége legyen. Itt van egy minta kód:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### K: Hogyan lehet beágyazott könyvjelzőt létrehozni a fő könyvjelzőn belül az Aspose.Words for .NET használatával?

 V: Ha beágyazott könyvjelzőt szeretne létrehozni egy fő könyvjelzőn belül az Aspose.Words for .NET használatával, használhatja ugyanezt`StartBookmark` és`EndBookmark` módszerek a beágyazott könyvjelző elindításához és befejezéséhez. Itt van egy minta kód:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### K: Hogyan adhatunk meg könyvjelző előnézeti szinteket egy kimeneti PDF-ben az Aspose.Words for .NET használatával?

 V: Ha a kimeneti PDF-ben az Aspose.Words for .NET használatával szeretné megadni a könyvjelző előnézeti szintjeit, használja a`PdfSaveOptions` osztály és a`BookmarksOutlineLevels` ingatlan. Hozzáadhat fő könyvjelzőket és beágyazott könyvjelzőket a megfelelő szintekkel. Itt van egy minta kód:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### K: Hogyan lehet elmenteni egy dokumentumot könyvjelzők létrehozása után az Aspose.Words for .NET használatával?

 V: Ha az Aspose.Words for .NET segítségével könyvjelzőket hozott létre, a dokumentum mentéséhez használja a`Save` módszere a`Document` objektum, amely megadja a célfájl elérési útját. Itt van egy minta kód:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### K: Hogyan adhatunk meg könyvjelző előnézeti szinteket egy kimeneti PDF-ben az Aspose.Words for .NET használatával?

 V: Ha a kimeneti PDF-ben az Aspose.Words for .NET használatával szeretné megadni a könyvjelző előnézeti szintjeit, használja a`PdfSaveOptions` osztály és a`BookmarksOutlineLevels` ingatlan. Hozzáadhat fő könyvjelzőket és beágyazott könyvjelzőket a megfelelő szintekkel. Itt van egy minta kód:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### K: Hogyan lehet beágyazott könyvjelzőket létrehozni egy fő könyvjelzőn belül az Aspose.Words for .NET használatával?

 V: Ha egy fő könyvjelzőn belül szeretne beágyazott könyvjelzőket létrehozni az Aspose.Words for .NET használatával, ugyanezt használhatja`StartBookmark` és`EndBookmark` módszerek a beágyazott könyvjelzők indításához és befejezéséhez. Ügyeljen arra, hogy a szülő könyvjelzőt adja meg paraméterként, amikor meghívja a`StartBookmark` módszer. Itt van egy minta kód:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### K: Hogyan lehet szöveget hozzáadni egy könyvjelzőhöz az Aspose.Words for .NET használatával?

 V: Ha szöveget szeretne hozzáadni egy könyvjelzőhöz az Aspose.Words for .NET használatával, használja a`Write` módszere a`DocumentBuilder`objektum, amely megadja a hozzáadandó szöveget. Itt van egy minta kód:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### K: Hogyan lehet főkönyvjelzőt létrehozni egy dokumentumban az Aspose.Words for .NET használatával?

 V: Ha egy dokumentumban fő könyvjelzőt szeretne létrehozni az Aspose.Words for .NET használatával, használja a`StartBookmark` módszer a könyvjelző elindításához és a`EndBookmark` módszer a megszüntetésére. Itt van egy minta kód:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```