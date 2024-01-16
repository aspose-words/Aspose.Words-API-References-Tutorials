---
title: Cím
linktitle: Cím
second_title: Aspose.Words Document Processing API
description: Ismerje meg a fejléc használatát az Aspose.Words for .NET programban Lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/heading/
---

Ebben a példában bemutatjuk, hogyan használhatja a címsor funkciót az Aspose.Words for .NET-hez. A fejlécek a dokumentum tartalmának strukturálására és rangsorolására szolgálnak.

## 1. lépés: Dokumentumgenerátor használata

Először egy dokumentumgenerátort fogunk használni, hogy tartalmat adjunk a dokumentumunkhoz.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. lépés: A címsorstílusok testreszabása

Alapértelmezés szerint a Word címsorstílusai félkövér és dőlt formázásúak lehetnek. Ha nem akarjuk, hogy ezek a tulajdonságok érvényesüljenek, akkor kifejezetten "false"-ra kell állítani őket.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## 3. lépés: 1. szintű cím hozzáadása

 1. szintű címet adhatunk hozzá a megfelelő bekezdésstílus nevének megadásával és a`Writeln` módszer a cím tartalmának megírásához.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

### Példa forráskódra az Aspose.Words .NET címsorhoz


```csharp
// Használjon dokumentumkészítőt, hogy tartalmat adjon a dokumentumhoz.
DocumentBuilder builder = new DocumentBuilder();

// Alapértelmezés szerint a Word címsorstílusai félkövér és dőlt formázással rendelkezhetnek.
//Ha nem akarjuk, hogy hangsúlyozzák, akkor ezeket a tulajdonságokat kifejezetten false értékre állítsuk.
builder.Font.Bold = false;
builder.Font.Italic = false;

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

Gratulálok ! Most megtanulta, hogyan kell használni a címsor funkciót az Aspose.Words for .NET-hez.

### GYIK

#### K: Mi az a Markdown fejléc?

V: A Markdown fejléc egy olyan elem, amely címsorok és alcímek létrehozására szolgál egy dokumentumban. A font (#) szimbólumok szintaxisát használja, amelyet szóköz és címszöveg követ.

#### K: Hogyan használhatom a Markdown címsorok különböző szintjeit?

V: A különböző szintű Markdown címsorok használatához különböző számú font (#) szimbólumot adhat hozzá a címsor szövege elé.

#### K: Vannak-e korlátozások a Markdown fejlécek használatában?

V: Nincsenek szigorú korlátozások, de ajánlott egy világos és tömör jelentési struktúra fenntartása.

#### K: Testreszabhatom a Markdown fejlécek megjelenését?

V: A szabványos Markdown-ban nem lehet testreszabni a Markdown fejlécek megjelenését, de néhány fejlett Markdown-bővítmény és szerkesztő további funkciókat kínál.

#### K: Minden Markdown-szerkesztő támogatja a Markdown címsorokat?

V: Igen, a legtöbb népszerű Markdown szerkesztő támogatja a Markdown fejléceket, de ellenőrizze a szerkesztő konkrét dokumentációját.