---
title: Állítsa be a relatív vízszintes vagy függőleges pozíciót
linktitle: Állítsa be a relatív vízszintes vagy függőleges pozíciót
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthatja be egy táblázat relatív vízszintes vagy függőleges helyzetét egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

Ebben az oktatóanyagban megtudjuk, hogyan lehet beállítani egy táblázat relatív vízszintes vagy függőleges helyzetét egy Word-dokumentumban az Aspose.Words for .NET segítségével. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Az oktatóanyag végére beállíthatja a táblázat relatív vízszintes vagy függőleges helyzetét a Word-dokumentumokban.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum betöltése
A szövegszerkesztés elindításához a dokumentummal, kövesse az alábbi lépéseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára, és adja meg a megfelelő fájlnevet.

## 3. lépés: Az asztal relatív helyzetének beállítása
Ezután beállítjuk a táblázat relatív vízszintes vagy függőleges helyzetét. Használja a következő kódot:

```csharp
// Vedd vissza az asztalt
Table table = doc.FirstSection.Body.Tables[0];

// táblázat relatív vízszintes helyzetének meghatározása
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Határozza meg a táblázat relatív függőleges helyzetét
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Itt a dokumentum segítségével lekérjük az első táblázatot az első szakasz törzséből. Ezután beállítjuk a táblázat relatív vízszintes helyzetét a`HorizontalAnchor` ingatlan segítségével a`RelativeHorizontalPosition.Column` érték. Hasonlóképpen beállítjuk a táblázat relatív függőleges helyzetét a`VerticalAnchor` ingatlan segítségével a`RelativeVerticalPosition.Page` érték.

## 4. lépés: Mentse el a módosított dokumentumot
Végül el kell mentenünk a módosított dokumentumot a táblázat relatív pozíciójával. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.

### Minta forráskód a relatív vízszintes vagy függőleges pozíció beállításához az Aspose.Words for .NET használatával 

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet beállítani egy táblázat relatív vízszintes vagy függőleges helyzetét egy Word-dokumentumban az Aspose.Words for .NET segítségével. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C# kódot, alkalmazhatja ezt a relatív pozíciót a Word-dokumentumok táblázataiban.