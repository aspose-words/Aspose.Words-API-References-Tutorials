---
title: Könyvjelzővel ellátott szöveg másolása Word dokumentumba
linktitle: Könyvjelzővel ellátott szöveg másolása Word dokumentumba
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan másolhat könyvjelző szöveget Word-dokumentumban egy másik dokumentumba az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-bookmarks/copy-bookmarked-text/
---

Ebben a cikkben megvizsgáljuk a fenti C# forráskódot, hogy megértsük, hogyan használhatjuk a Könyvjelzővel ellátott szöveg másolása funkciót az Aspose.Words for .NET könyvtárban. Ez a funkció lehetővé teszi egy adott könyvjelző tartalmának átmásolását egy forrásdokumentumból egy másik dokumentumba.

## Előfeltételek

- C# nyelv alapismerete.
- .NET fejlesztői környezet telepített Aspose.Words könyvtárral.

## 1. lépés: Forrásdokumentum betöltése

 A könyvjelző szövegének másolása előtt be kell töltenünk a forrásdokumentumot a`Document` objektum a fájl elérési útját használva:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## 2. lépés: Forrás könyvjelző lekérése

 Használjuk a`Bookmarks` a forrásdokumentum tartomány tulajdonsága, hogy megkapjuk a másolni kívánt könyvjelzőt:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## 3. lépés: A céldokumentum létrehozása

Létrehozunk egy új dokumentumot, amely céldokumentumként fog szolgálni a könyvjelző tartalmának másolásához:

```csharp
Document dstDoc = new Document();
```

## 4. lépés: A másolás helyének megadása

Megadjuk azt a helyet, ahová a másolt szöveget hozzá szeretnénk adni. Példánkban a szöveget hozzáadjuk a céldokumentum utolsó szakaszának törzsének végéhez:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## 5. lépés: Importálja és másolja a könyvjelző szövegét

 Használjuk a`NodeImporter`objektum a könyvjelző szövegének importálásához és másolásához a forrásdokumentumból a céldokumentumba:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Példa forráskódra a könyvjelzővel ellátott szöveg másolásához az Aspose.Words segítségével .NET-hez

Íme a teljes példaforráskód a könyvjelzők szövegének másolásának bemutatására az Aspose.Words for .NET használatával:

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Ez az a könyvjelző, amelynek tartalmát másolni szeretnénk.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Ezt a dokumentumot kiegészítjük.
	Document dstDoc = new Document();

	// Tegyük fel, hogy az utolsó szakasz törzsének végéhez leszünk hozzáfűzve.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Ha többször importál egyetlen kontextus nélkül, akkor sok stílus jön létre.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### AddBookmarkedText forráskód

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
            // Ez az a bekezdés, amely a könyvjelző elejét tartalmazza.
            Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

            // Ez az a bekezdés, amely a könyvjelző végét tartalmazza.
            Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

            if (startPara == null || endPara == null)
                throw new InvalidOperationException(
                    "Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

            // Korlátozzuk magunkat egy meglehetősen egyszerű forgatókönyvre.
            if (startPara.ParentNode != endPara.ParentNode)
                throw new InvalidOperationException(
                    "Start and end paragraphs have different parents, cannot handle this scenario yet.");

            // Minden bekezdést át akarunk másolni a kezdő bekezdéstől a záró bekezdésig (beleértve),
            // ezért a csomópont, amelynél megállunk, egy a bekezdés végének után van.
            Node endNode = endPara.NextSibling;

            for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
            {
                //Ez létrehozza az aktuális csomópont másolatát, és importálja (érvényessé teszi) a kontextusba
                // a rendeltetési okmány. Az importálás a stílusok és a listaazonosítók helyes beállítását jelenti.
                Node newNode = importer.ImportNode(curNode, true);

                dstNode.AppendChild(newNode);
            }
        }

```
## Következtetés

Ebben a cikkben megvizsgáltuk a C# forráskódot, hogy megértsük, hogyan kell használni a Könyvjelzővel ellátott szöveg másolása az Aspose.Words for .NET-ből funkciót. A könyvjelző tartalmának forrásdokumentumból egy másik dokumentumba való másolásához lépésről lépésre követtük.

### GYIK a könyvjelzővel ellátott szöveg Word dokumentumba másolásához

#### K: Mik a követelmények az Aspose.Words for .NET "Szöveg másolása könyvjelzőkkel" funkció használatához?

V: Az Aspose.Words for .NET "Szöveg másolása könyvjelzőkkel" funkciójának használatához alapszintű C# nyelvtudással kell rendelkeznie. Szüksége van egy .NET fejlesztői környezetre is, amelyen az Aspose.Words könyvtár telepítve van.

#### K: Hogyan tölthetek be forrásdokumentumot az Aspose.Words for .NET-be?

 V: Forrásdokumentum betöltéséhez az Aspose.Words for .NET-be a`Document` osztályba a dokumentum fájl elérési útjának megadásával. Itt van egy minta kód:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### K: Hogyan szerezhető be egy adott könyvjelző tartalma egy forrásdokumentumban az Aspose.Words for .NET használatával?

 V: Egy adott könyvjelző tartalmának forrásdokumentumban való megjelenítéséhez az Aspose.Words for .NET használatával elérheti a`Bookmarks` a forrásdokumentum tartomány tulajdonságát, és használja a könyvjelző nevét az adott könyvjelző lekéréséhez. Itt van egy minta kód:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### K: Hogyan lehet megadni a könyvjelző szövegmásolatának helyét a céldokumentumban az Aspose.Words for .NET használatával?

 V: Ha az Aspose.Words for .NET használatával szeretné megadni, hogy hova kívánja hozzáadni a másolt könyvjelzőszöveget a céldokumentumban, navigáljon a céldokumentum utolsó szakaszához. Használhatja a`LastSection` tulajdonság eléréséhez az utolsó szakaszt és a`Body` tulajdonság eléréséhez az adott szakasz törzséhez. Itt van egy minta kód:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### K: Hogyan importálhatunk és másolhatunk könyvjelző szöveget a forrásdokumentumból a céldokumentumba az Aspose.Words for .NET használatával?

 V: A könyvjelzőszöveg forrásdokumentumból a céldokumentumba történő importálásához és másolásához az Aspose.Words for .NET használatával, használhatja a`NodeImporter` osztály, amely megadja a forrásdokumentumot, a céldokumentumot és a megtartandó formázási módot. Ezután használhatja a`AppendBookmarkedText` módszert a könyvjelzőszöveg hozzáadásához a céldokumentumhoz. Itt van egy minta kód:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### K: Hogyan lehet elmenteni egy céldokumentumot a könyvjelzőszöveg Aspose.Words for .NET segítségével történő másolása után?

V: A céldokumentum mentéséhez, miután az Aspose.Words for .NET segítségével másolt szöveget egy könyvjelzőből, használja a`Save` módszere a`Document` objektum, amely megadja a célfájl elérési útját. Itt van egy minta kód:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```