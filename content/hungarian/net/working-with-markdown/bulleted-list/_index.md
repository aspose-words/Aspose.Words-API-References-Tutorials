---
title: Felsorolásos lista
linktitle: Felsorolásos lista
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre felsorolásjeles listát az Aspose.Words for .NET segítségével Lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/bulleted-list/
---

Ebben az oktatóanyagban bemutatjuk, hogyan hozhat létre felsorolásjeles listát az Aspose.Words for .NET segítségével. A felsorolásjeles lista az elemek felsorolására szolgál számozás nélkül.

## 1. lépés: Dokumentumgenerátor használata

Először egy dokumentumgenerátort fogunk használni, hogy tartalmat adjunk a dokumentumunkhoz.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. lépés: Alapértelmezett felsorolásjeles lista alkalmazása

 Alkalmazhatunk egy alapértelmezett felsorolásjeles listát a dokumentumkészítő segítségével`ApplyBulletDefault` módszer.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## 3. lépés: A listajel formátum testreszabása

 Testreszabhatjuk a felsorolás formátumát a tulajdonságok elérésével`ListFormat.List.ListLevels[0]`. Ebben a példában a "-" kötőjelet használjuk felsorolásjelként.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## 4. lépés: Elemek hozzáadása a listához

 Most hozzáadhatunk elemeket a felsorolt listához a dokumentumkészítő segítségével`Writeln` módszer.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## 5. lépés: A behúzás eltávolítása a listából

 Ha részlistát akarunk létrehozni, a behúzást a segítségével növelhetjük`ListFormat.ListIndent()` módszer. Ebben a példában egy allistát adunk a 2a és 2b elemekhez.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Példa forráskód a felsorolásjeles listához az Aspose.Words for .NET használatával


```csharp
// Használjon dokumentumkészítőt, hogy tartalmat adjon a dokumentumhoz.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Gratulálok ! Most megtanulta, hogyan hozhat létre felsorolásjeles listát az Aspose.Words for .NET segítségével.

### GYIK

#### K: Hogyan készítsünk felsorolásjeles listát a Markdownban?

V: Ha a Markdown alkalmazásban felsorolásjeles listát szeretne létrehozni, kezdje az egyes listaelemeket egy felsorolásjellel (`-`, `*` , vagy`+`), szóköz követi.

#### K: Beágyazhatok felsorolásjeles listákat a Markdownba?

V: Igen, lehetőség van felsorolásjeles listák egymásba ágyazására a Markdown alkalmazásban négy eltolási szóköz hozzáadásával minden beágyazott listaelem elé.

#### K: Hogyan lehet testreszabni a felsorolásjeleket?

V: A szabványos Markdownban a felsorolásjelek előre meghatározottak. Egyes Markdown szerkesztők azonban lehetővé teszik, hogy testre szabhassa őket meghatározott bővítmények segítségével.

#### K: A Markdown felsorolásjeles listái támogatják a behúzást?

V: Igen, a Markdown felsorolásjeles listái támogatják a behúzást. Balra eltolást szóközök vagy tabulátorok használatával adhat hozzá.

#### K: Hozzá lehet adni linkeket vagy szövegközi szöveget a listaelemekhez?

V: Igen, a megfelelő Markdown szintaxis használatával linkeket vagy szövegközi szöveget is hozzáadhat a listaelemekhez.
