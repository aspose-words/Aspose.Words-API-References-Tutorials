---
title: Meta karakterek a keresési mintában
linktitle: Meta karakterek a keresési mintában
second_title: Aspose.Words Document Processing API
description: Tanulja meg, hogyan lehet metakaraktereket használni a keresési mintában az Aspose.Words for .NET segítségével Word-dokumentumok kezeléséhez.
type: docs
weight: 10
url: /hu/net/find-and-replace-text/meta-characters-in-search-pattern/
---
Ebben a cikkben megvizsgáljuk a fenti C# forráskódot, hogy megértsük, hogyan használhatjuk a Meta Characters In Search Pattern funkciót az Aspose.Words for .NET könyvtárban. Ez a funkció lehetővé teszi speciális metakarakterek használatát speciális keresések és cserék végrehajtásához a Word dokumentumokban.

## Előfeltételek

- C# nyelv alapismerete.
- .NET fejlesztői környezet telepített Aspose.Words könyvtárral.

## 1. lépés: Új dokumentum létrehozása

 Mielőtt elkezdené a metakarakterek használatát a keresési mintában, létre kell hoznunk egy új dokumentumot az Aspose.Words for .NET használatával. Ez megtehető az a. példányosításával`Document` tárgy:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## 2. lépés: Szúrjon be szöveget a dokumentumba

 Ha megvan a dokumentumunk, szöveget szúrhatunk be az a segítségével`DocumentBuilder` tárgy. Példánkban a`Writeln` és`Write` kétsoros szöveg beszúrásának módjai:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## 3. lépés: Keresse meg és cserélje ki a szöveget metakarakterekre

 Most a`Range.Replace` funkcióval kereshet és cserélhet szöveget speciális metakaraktereket tartalmazó keresési mintával. Példánkban az "Ez az 1. sor és a pEz a 2. sor" kifejezést a "Ez a sor lecserélve" kifejezésre cseréljük a`&p` a bekezdéstörést jelző metakarakter:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## 4. lépés: Oldaltörés beszúrása a dokumentumba

 Egy másik metakarakter használatának szemléltetésére oldaltörést szúrunk be a dokumentumba a segítségével`InsertBreak` módszerrel a`BreakType.PageBreak` paraméter. Először mozgatjuk a kurzort a`DocumentBuilder` a dokumentum végére, majd beillesztjük az oldaltörést és egy új szövegsort:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## 5. lépés: Keressen és cseréljen másik metakarakterre

 Most egy újabb keresést hajtunk végre, és a helyettesítést a`&m` metakarakter, amely egy oldaltörést jelent. Az "Ez az 1. sor és mEz a 2. sor" kifejezést a következőre cseréljük: "Az oldaltörést új szöveg helyettesíti." :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## 6. lépés: A szerkesztett dokumentum mentése

Végül a módosított dokumentumot a megadott könyvtárba mentjük a`Save` módszer:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Példa forráskódra a Meta karakterek keresési mintában az Aspose.Words for .NET használatával

Íme a teljes minta forráskód, amely bemutatja a metakarakterek használatát az Aspose.Words for .NET keresési mintájában:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## Következtetés

Ebben a cikkben megvizsgáltuk a C# forráskódot, hogy megértsük, hogyan lehet metakaraktereket használni az Aspose.Words for .NET keresési mintájában. Lépésről lépésre követtük a dokumentum létrehozását, szöveg beszúrását, keresést és cserét speciális metakarakterek használatával, oldaltörések beszúrását és a szerkesztett dokumentum mentését.

### GYIK

#### K: Mi az Aspose.Words for .NET Meta Characters In Search Pattern szolgáltatása?

V: Az Aspose.Words for .NET Meta Characters In Search Pattern funkciója lehetővé teszi speciális metakarakterek használatát Word-dokumentumokban végzett speciális keresések és cserék végrehajtásához. Ezek a metakarakterek lehetővé teszik a bekezdéstörések, szakasztörések, oldaltörések és egyéb speciális elemek megjelenítését a keresési mintában.

#### K: Hogyan lehet új dokumentumot létrehozni az Aspose.Words for .NET-ben?

 V: Mielőtt metakaraktereket használna a keresési sablonban, létre kell hoznia egy új dokumentumot az Aspose.Words for .NET használatával. Ez megtehető az a. példányosításával`Document` tárgy. Íme egy mintakód egy új dokumentum létrehozásához:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### K: Hogyan lehet szöveget beszúrni egy dokumentumba az Aspose.Words for .NET használatával?

 V: Ha megvan a dokumentum, akkor a a segítségével illeszthet be szöveget`DocumentBuilder` tárgy. Példánkban a`Writeln` és`Write` kétsoros szöveg beszúrásának módjai:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### K: Hogyan lehet szöveget metakarakterekkel keresni és helyettesíteni egy dokumentumban az Aspose.Words for .NET használatával?

 V: Szöveg metakarakterekkel való kereséséhez és helyettesítéséhez használja a`Range.Replace` módszer. Példánkban az "Ez az 1. sor és a pEz a 2. sor" kifejezést a "Ez a sor lecserélve" kifejezésre cseréljük a`&p` a bekezdéstörést jelző metakarakter:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### K: Hogyan lehet oldaltörést beszúrni egy dokumentumba az Aspose.Words for .NET használatával?

V: Egy másik metakarakter használatának szemléltetésére oldaltörést szúrunk be a dokumentumba a segítségével`InsertBreak` módszerrel a`BreakType.PageBreak` paraméter. Először mozgatjuk a kurzort a`DocumentBuilder` a dokumentum végére, majd beillesztjük az oldaltörést és egy új szövegsort:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### K: Hogyan kereshet és cserélhet le egy másik metakaraktert egy dokumentumban az Aspose.Words for .NET használatával?

 V: Most újabb keresést hajtunk végre, és a helyettesítést a`&m` metakarakter, amely egy oldaltörést jelent. Az "Ez az 1. sor és mEz a 2. sor" kifejezést a következőre cseréljük: "Az oldaltörést új szöveg helyettesíti." :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### K: Hogyan lehet elmenteni a szerkesztett dokumentumot az Aspose.Words for .NET-be?

 V: Miután módosította a dokumentumot, elmentheti azt egy megadott könyvtárba a segítségével`Save` módszer:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```