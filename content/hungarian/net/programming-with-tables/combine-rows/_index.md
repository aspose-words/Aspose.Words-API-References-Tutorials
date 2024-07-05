---
title: Sorok kombinálása
linktitle: Sorok kombinálása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan kombinálhat táblázatsorokat egy Word-dokumentumban az Aspose.Words for .NET programmal.
type: docs
weight: 10
url: /hu/net/programming-with-tables/combine-rows/
---

Ebben az oktatóanyagban megtanuljuk, hogyan lehet az Aspose.Words for .NET-et használni táblázatsorok egyesítésére egy Word-dokumentumban. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Ennek az oktatóanyagnak a végén programozottan kezelheti és egyesítheti a Word-dokumentumok táblázatsorait.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum betöltése és a táblázatok elérése
táblázatokkal történő szövegfeldolgozás elindításához be kell töltenünk az azokat tartalmazó dokumentumot, és el kell érnünk őket. Kovesd ezeket a lepeseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot
Document doc = new Document(dataDir + "Tables.docx");

// Hozzáférés az asztalokhoz
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 3. lépés: A táblázat sorainak kombinálása
Ezután összevonjuk a második táblázat sorait az első tábla végével. Használja a következő kódot:

```csharp
// Táblázatsorok kombinációja
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Itt használjuk a`while` ciklus, hogy a második tömb összes sorát ismételje, és hozzáadja őket az első tömb végéhez a`Add` módszer. Ezután eltávolítjuk a második táblázatot a dokumentumból a`Remove` módszer.

## 4. lépés: Mentse el a módosított dokumentumot
Végül el kell mentenünk a módosított dokumentumot a kombinált táblázatsorokkal. Használja a következő kódot:

```csharp
// Mentse el a módosított dokumentumot
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.

### Minta forráskód a Combine Rows használatához Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// A második táblázat sorai az első táblázat végéhez lesznek hozzáfűzve.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Az aktuális táblázat összes sorának hozzáfűzése a következő táblázatokhoz
	// Különböző cellaszámú és szélességű elemek egy táblázatba illeszthetők.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kombinálhatunk táblázatsorokat egy Word-dokumentumban az Aspose.Words for .NET használatával. Ha követi ezt a lépésről lépésre szóló útmutatót, és implementálja a mellékelt C# kódot, akkor programozottan módosíthatja a Word-dokumentumok táblázatsorait. Ezzel a funkcióval hatékonyan egyesítheti és táblázatba rendezheti adatait.