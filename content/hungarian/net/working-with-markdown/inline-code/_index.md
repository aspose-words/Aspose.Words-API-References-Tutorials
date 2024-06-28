---
title: Inline kód
linktitle: Inline kód
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan írhat be kódot az Aspose.Words for .NET segítségével Lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/inline-code/
---

Ebben a példában bemutatjuk, hogyan használhatja a soron belüli kód funkciót az Aspose.Words for .NET-hez. A soron belüli kód a bekezdésen belüli kódrészletek vizuális megjelenítésére szolgál.

## 1. lépés: Dokumentumgenerátor használata

Először egy dokumentumgenerátort fogunk használni, hogy tartalmat adjunk a dokumentumunkhoz.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. lépés: Stílus hozzáadása a soron belüli kódhoz

 Egyéni stílust adunk hozzá a soron belüli kódhoz a segítségével`Styles.Add` módszere a`Document` tárgy. Ebben a példában egy "InlineCode" nevű stílust hozunk létre a soron belüli kódhoz, alapértelmezett backtick-el.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## 3. lépés: Adjon hozzá szövegközi kódot

Most hozzáadhatunk soron belüli kódot az "InlineCode" egyéni stílus használatával. Ebben a példában két szövegrészt adunk hozzá különböző számú backtick-el.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Példa forráskód az Inline kódhoz az Aspose.Words .NET-hez

```csharp
// Használjon dokumentumkészítőt, hogy tartalmat adjon a dokumentumhoz.
DocumentBuilder builder = new DocumentBuilder();

// A backtickek száma kimaradt, alapértelmezés szerint egy backtick kerül felhasználásra.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// 3 backtick lesz.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

Gratulálok ! Most megtanulta, hogyan kell használni a soron belüli kódfunkciókat az Aspose.Words for .NET-hez.


### GYIK

#### K: Hogyan használhatom az Aspose.Words szövegközi kódját?

 V: Az Aspose.Words szövegközi kód használatához megfelelő címkéket használhat a beágyazott kódként formázandó szöveg körül. Használhatja például a`<code>` vagy`<kbd>` tag a körülvevő szöveghez, amelyet soron belüli kódként kell formázni.

#### K: Megadható-e soron belüli kód betűtípusa vagy színe az Aspose.Words-ben?

 V: Igen, megadhatja a soron belüli kód betűtípusát vagy színét az Aspose.Words-ben. Használhatja a`Font.Name` és`Font.Color` tulajdonságai a`Run` objektum a soron belüli kód betűtípusának és színének beállításához. Például használhatja`run.Font.Name = "Courier New"` a szövegközi kód betűtípusának megadásához és`run.Font.Color = Color.Blue` szín megadásához.

#### K: Használhatom a soron belüli kódot olyan bekezdésben, amely más szövegelemeket tartalmaz?

 V: Igen, használhatja a szövegközi kódot egy olyan bekezdésben, amely más szövegelemeket tartalmaz. Többet is létrehozhat`Run` objektumok a bekezdés különböző részeit ábrázolják, majd a soron belüli kódcímkékkel csak az adott részeket formázza soron belüli kódként. Ezután hozzáadhatja őket a bekezdéshez a`Paragraph.AppendChild(run)` módszer.