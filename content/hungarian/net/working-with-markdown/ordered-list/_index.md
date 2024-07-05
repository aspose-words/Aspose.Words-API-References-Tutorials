---
title: Rendezett lista
linktitle: Rendezett lista
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre rendezett listát az Aspose.Words for .NET segítségével Lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/ordered-list/
---

Ebben a példában elmagyarázzuk, hogyan használható a rendezett lista funkció az Aspose.Words for .NET-ben. A Rendezett lista lehetővé teszi az elemek sorba rendezését számokkal.

## 1. lépés: Dokumentumgenerátor használata

Először egy dokumentumgenerátort fogunk használni egy új dokumentum létrehozásához.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: A rendezett listaformátum alkalmazása

 A megrendelt listaformátumot a dokumentumkészítő segítségével alkalmazzuk`ApplyBulletDefault`módszer. A számozási formátumot is testreszabhatjuk, ha a listaszintekre lépünk, és beállítjuk a kívánt formátumot.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## 3. lépés: Tételek hozzáadása a listához

 A listához tételeket a dokumentumgenerátor segítségével tudunk felvenni`Writeln` módszer.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## 4. lépés: húzza be a listát

 A listát a dokumentumgenerátor segítségével behúzhatjuk`ListIndent` módszer.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## 5. lépés: A dokumentum mentése

Végül elmenthetjük a dokumentumot a kívánt formátumban.

### Példa forráskódra rendezett listához az Aspose.Words for .NET-hez

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Gratulálok ! Most megtanulta, hogyan kell használni a rendezett lista funkciót az Aspose.Words for .NET-hez.


### GYIK

#### K: Hogyan lehet rendezett listát létrehozni a Markdownban?

V: Ha rendezett listát szeretne létrehozni a Markdown alkalmazásban, minden listaelemet kezdjen egy számmal, majd egy ponttal (`1.`, `2.`, `3.`), szóköz követi.

#### K: Beágyazhatunk rendezett listákat a Markdownba?

V: Igen, lehetőség van rendezett listák egymásba ágyazására a Markdown alkalmazásban úgy, hogy minden beágyazott listaelem elé négy eltolási szóközt ad.

#### K: Hogyan lehet testreszabni a rendezett listák számozását?

V: A szabványos Markdown esetén a rendezett listaszámozás automatikusan generálódik. Egyes Markdown szerkesztők azonban lehetővé teszik, hogy testre szabhassa bizonyos bővítmények segítségével.

#### K: Támogatják a Markdown rendezett listái a behúzást?

V: Igen, a Markdown-ban lévő rendezett listák támogatják a behúzást. Balra eltolást szóközök vagy tabulátorok használatával adhat hozzá.

#### K: Hozzá lehet adni linkeket vagy szövegközi szöveget a listaelemekhez?

V: Igen, a megfelelő Markdown szintaxis használatával linkeket vagy szövegközi szöveget is hozzáadhat a listaelemekhez.