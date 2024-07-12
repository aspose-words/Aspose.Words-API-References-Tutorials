---
title: Preferált szélességtípus lekérése
linktitle: Preferált szélességtípus lekérése
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan kérheti le egy cella típusát és preferált szélességi értékét Word-táblázatban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/retrieve-preferred-width-type/
---

Ebben az oktatóanyagban megtanuljuk, hogyan lehet lekérni a preferált szélességtípust és annak értékét egy Word-dokumentum táblázatcellájából az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Az oktatóanyag végén lekérheti az előnyben részesített szélességtípust (abszolút, relatív vagy automatikus) és értékét a Word-dokumentumtáblázatok egy adott cellájához.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum betöltése
A szövegszerkesztés elindításához a dokumentummal, kövesse az alábbi lépéseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot
Document doc = new Document(dataDir + "Tables.docx");
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára, és adja meg a megfelelő fájlnevet.

## 3. lépés: A kívánt szélességtípus és érték lekérése
Ezután lekérjük a kívánt szélességtípust és annak értékét egy adott táblázatcellához. Használja a következő kódot:

```csharp
// Vedd vissza az asztalt
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Aktiválja az automatikus asztal beállítást
table. AllowAutoFit = true;

//Az első sor első cellájának lekérése
Cell firstCell = table.FirstRow.FirstCell;

// Keresse meg a kívánt szélességtípust és annak értékét
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

 Itt a dokumentumot használjuk az első táblázat lekérésére, majd engedélyezzük az automatikus táblázatillesztést a`AllowAutoFit` ingatlan. Ezután lekérjük a táblázat első sorának első celláját. Ebből a cellából lekérhetjük a kívánt szélességtípust a`PreferredWidth.Type` ingatlan és annak értéke a`PreferredWidth.Value` ingatlan.

### Minta forráskód a Retrieve Preferred Width Type funkcióhoz az Aspose.Words for .NET használatával 

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet lekérni a preferált szélességtípust és annak értékét egy Word-dokumentum táblázatcellájából az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C# kódot, lekérheti ezeket az információkat a Word dokumentumtáblázataiban lévő egyes cellákhoz.