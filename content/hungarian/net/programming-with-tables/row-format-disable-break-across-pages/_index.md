---
title: Sorformátum Az oldalak közötti törés letiltása
linktitle: Sorformátum Az oldalak közötti törés letiltása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan lehet letiltani a sortörést egy többoldalas táblázatban egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/row-format-disable-break-across-pages/
---

Ebben az oktatóanyagban megtudjuk, hogyan lehet letiltani egy többoldalas táblázat sortörését egy Word-dokumentumban az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Ennek az oktatóanyagnak a végére letilthatja a sortörést a Word-dokumentumok táblázatának összes sorában.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum betöltése
A szövegszerkesztés elindításához a dokumentummal, kövesse az alábbi lépéseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára, és adja meg a megfelelő fájlnevet.

## 3. lépés: A táblázat sortörésének letiltása
Ezután a táblázat összes sorában letiltjuk a sortörést. Használja a következő kódot:

```csharp
// Vedd vissza az asztalt
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// A sortörés letiltása a táblázat összes sorában
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Itt a dokumentumot használjuk az első tábla lekérésére, majd a tábla összes sorát egy foreach ciklus segítségével iteráljuk. A cikluson belül minden sornál letiltjuk a sortörést a`RowFormat.AllowBreakAcrossPages`tulajdonát`false`.

## 4. lépés: Mentse el a módosított dokumentumot
Végül el kell mentenünk a módosított dokumentumot a táblázat sortörésének letiltásával. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.

### Minta forráskód a sorformátumhoz Az oldaltörés letiltása az Aspose.Words for .NET használatával 

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Az oldalak közötti törés letiltása a táblázat összes sorában.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet letiltani egy többoldalas táblázat sortörését egy Word-dokumentumban az Aspose.Words for .NET használatával. Ha követi ezt a lépésről lépésre szóló útmutatót, és implementálja a mellékelt C# kódot, ezt a tiltást alkalmazhatja a Word-dokumentumokban lévő táblákon.