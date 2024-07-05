---
title: Könyvjelzők elrejtése a Word-dokumentumban
linktitle: Könyvjelzők elrejtése a Word-dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan jeleníthet meg vagy rejthet el egy adott könyvjelzőt Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-bookmarks/show-hide-bookmarks/
---

Ebben a cikkben megvizsgáljuk a fenti C# forráskódot, hogy megértsük, hogyan kell használni a Könyvjelzők elrejtése funkciót az Aspose.Words for .NET könyvtárban. Ez a funkció lehetővé teszi egy adott könyvjelző megjelenítését vagy elrejtését a Word dokumentumban.

## Előfeltételek

- C# nyelv alapismerete.
- .NET fejlesztői környezet telepített Aspose.Words könyvtárral.

## 1. lépés: A dokumentum betöltése

 Használjuk a`Document` osztály a meglévő dokumentum fájlból való betöltéséhez:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## 2. lépés: Adott könyvjelző megjelenítése vagy elrejtése

 Használjuk a`ShowHideBookmarkedContent` funkció egy adott könyvjelző megjelenítéséhez vagy elrejtéséhez a dokumentumban. Ez a függvény paraméterként veszi a dokumentumot, a könyvjelző nevét és egy logikai értéket, amely jelzi, hogy a könyvjelzőt megjeleníteni vagy elrejteni:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## 3. lépés: Mentse el a módosított dokumentumot

 Használjuk a`Save` módszer a módosított dokumentum fájlba mentéséhez:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Példa forráskódra a Könyvjelzők elrejtése az Aspose.Words segítségével .NET-hez

Íme a teljes példaforráskód, amely bemutatja egy adott könyvjelző megjelenítését vagy elrejtését az Aspose.Words for .NET használatával:

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### ShowHideBookmarkedContent forráskód

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
            Bookmark bm = doc.Range.Bookmarks[bookmarkName];

            DocumentBuilder builder = new DocumentBuilder(doc);
            builder.MoveToDocumentEnd();

            // {IF "{MERGEFIELD könyvjelző}" = "igaz" "" ""}
            Field field = builder.InsertField("IF \"", null);
            builder.MoveTo(field.Start.NextSibling);
            builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
            builder.Write("\" = \"true\" ");
            builder.Write("\"");
            builder.Write("\"");
            builder.Write(" \"\"");

            Node currentNode = field.Start;
            bool flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.Run)
                    if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
                        flag = false;

                Node nextNode = currentNode.NextSibling;

                bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
                currentNode = nextNode;
            }

            Node endNode = bm.BookmarkEnd;
            flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.FieldEnd)
                    flag = false;

                Node nextNode = currentNode.NextSibling;

                bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
                endNode = currentNode;
                currentNode = nextNode;
            }

            doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });
        }
		
```
## Következtetés

Ebben a cikkben megvizsgáltuk a C# forráskódot, hogy megértsük, hogyan használható az Aspose.Words for .NET Könyvjelzők elrejtése funkciója. Egy adott könyvjelző megjelenítéséhez vagy elrejtéséhez lépésről lépésre követtük a dokumentumot.

### GYIK a könyvjelzők elrejtéséhez a Word dokumentumban

#### K: Megjeleníthetek vagy elrejthetek több könyvjelzőt ugyanabban a dokumentumban?

V: Igen, több könyvjelzőt is megjeleníthet vagy elrejthet ugyanabban a dokumentumban a 2. és 3. lépés megismétlésével minden feldolgozni kívánt könyvjelzőnél.

#### K: Működik a mellékelt kód más Word-dokumentumformátumokkal, például .doc vagy .docm?

V: Igen, a mellékelt kód az Aspose.Words által támogatott különféle Word-dokumentumformátumokkal működik, mint például a .doc és a .docm. Csak ügyeljen arra, hogy a megfelelő fájlnevet és elérési utat használja a dokumentum betöltésekor és mentésekor.

#### K: Hogyan jeleníthetek meg újra egy rejtett könyvjelzőt?

 V: A rejtett könyvjelző ismételt megjelenítéséhez ugyanazt kell használnia`ShowHideBookmarkedContent` függvény átadja az értéket`true` a logikai paraméterhez, amely jelzi, hogy meg kell-e mutatni vagy el kell rejteni a könyvjelzőt.

#### K: Használhatok feltételeket a könyvjelzők megjelenítésére vagy elrejtésére a dokumentumban lévő egyesítő mezők értékei alapján?

 V: Igen, feltételekkel és egyesítheti a mezőértékeket annak meghatározására, hogy a könyvjelző megjelenjen-e vagy elrejtve. Testreszabhatja a kódot`ShowHideBookmarkedContent` függvényében figyelembe kell venni a megfelelő feltételeket és értékeket.

#### K: Hogyan törölhetek egy könyvjelzőt egy Word-dokumentumból az Aspose.Words for .NET használatával?

 V: Könyvjelző eltávolításához Word-dokumentumból az Aspose.Words for .NET használatával, használja a`RemoveBookmarks` módszere a`Document` osztály. Itt van egy minta kód:

```csharp
doc.RemoveBookmarks("BookmarkName");
```