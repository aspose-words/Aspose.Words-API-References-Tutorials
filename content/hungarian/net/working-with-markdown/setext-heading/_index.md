---
title: Setex címsor
linktitle: Setex címsor
second_title: Aspose.Words Document Processing API
description: Az Aspose.Words for .NET segítségével megtudhatja, hogyan használhatja a Setext fejlécet a dokumentumok formázására az Aspose.Words for .NET segítségével – lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/setext-heading/
---

Ebben az oktatóanyagban végigvezetjük, hogyan használhatja a Setext Heading funkciót az Aspose.Words for .NET-hez. A Setext Heading egy alternatív módszer a címek formázására a Markdown dokumentumokban.

## 1. lépés: Dokumentumgenerátor használata

Először egy dokumentumgenerátort fogunk használni, hogy tartalmat adjunk a dokumentumunkhoz.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## 2. lépés: A Setext címsor stílusának használata

Az alapértelmezett "Címsor 1" bekezdésstílust fogjuk használni, hogy 1. szintű címsort hozzunk létre a dokumentumunkban.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## 3. lépés: Stílusok visszaállítása

Visszaállítjuk a korábban alkalmazott betűstílusokat, hogy elkerüljük a stílusok nem kívánt kombinációit a bekezdések között.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## 4. lépés: A Setext címsorszintek testreszabása

Testreszabhatjuk a Setext címsorszinteket új bekezdésstílusok hozzáadásával a meglévő címstílusok alapján. Ebben a példában létrehozunk egy "SetextHeading1" stílust a "Heading 1" stíluson alapulva, hogy az 1. szintű címsort jelenítse meg a Setext formátumban.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## 5. lépés: A dokumentum mentése

Végül elmenthetjük a dokumentumot a kívánt formátumban.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Példa forráskód Setext címekhez Aspose.Words for .NET-hez

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Használjon dokumentumkészítőt, hogy tartalmat adjon a dokumentumhoz.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// Állítsa vissza a stílusokat az előző bekezdésből, hogy ne keverje össze a stílusokat a bekezdések között.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// Állítsa vissza a stílusokat az előző bekezdésből, hogy ne keverje össze a stílusokat a bekezdések között.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// A Setex címsorszintje 2-re áll vissza, ha az alapbekezdés címsorszintje nagyobb, mint 2.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### GYIK

#### K: Mi az a Setext Markdown fejléc?

V: A Setext Markdown fejléc egy alternatív módja a címsorok létrehozásának egy Markdown dokumentumban. Aláhúzás karaktereket (= vagy -) használ a címsorok különböző szintjei jelzésére.

#### K: Hogyan kell használni a Setext Markdown fejléceket?

V: A Setext Markdown fejlécek használatához helyezzen aláhúzásjelet a cím szövege alá. Használjon egyenlőségjelet (=) az 1. szintű fejléchez, és kötőjelet (-) a 2. szintű fejléchez.

#### K: Vannak-e korlátozások a Setext Markdown fejlécek használatában?

V: A Setext Markdown címsorok a címsorhierarchiát illetően korlátozottak, és vizuálisan nem különböznek annyira, mint a szabványos Markdown címsorok.

#### K: Testreszabhatom a Setext Markdown fejlécek megjelenését?

V: A szabványos Markdownban nem lehet testreszabni a Setext Markdown fejlécek megjelenését. Előre meghatározott megjelenésűek a használt aláhúzás karakterek alapján.

#### K: Az összes Markdown szerkesztő támogatja a Setext Markdown fejléceket?

V: A Setext Markdown fejlécek támogatása Markdown szerkesztőnként eltérő lehet. Ellenőrizze a kiadója konkrét dokumentációját, hogy megbizonyosodjon róla.