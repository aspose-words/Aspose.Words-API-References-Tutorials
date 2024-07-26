---
title: Teljes táblázat klónozása
linktitle: Teljes táblázat klónozása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan klónozhat egy teljes táblázatot Word-dokumentumba az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/clone-complete-table/
---

Ebben az oktatóanyagban megtanuljuk, hogyan kell az Aspose.Words for .NET használatával egy teljes táblázatot Word dokumentumba klónozni. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Ennek az oktatóanyagnak a végén programozottan klónozhat táblázatokat Word-dokumentumaiba.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum betöltése és a táblázat elérése
A Szövegfeldolgozás elindításához a táblázattal be kell töltenünk az azt tartalmazó dokumentumot, és hozzá kell férnünk. Kovesd ezeket a lepeseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot
Document doc = new Document(dataDir + "Tables.docx");

// Hozzáférés a tömbhöz
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 3. lépés: Teljes tömb klónozás
Ezután a teljes táblázatot klónozzuk, és beillesztjük a dokumentumba az eredeti után. Használja a következő kódot:

```csharp
// Klónozza a tömböt
Table tableClone = (Table)table.Clone(true);

// Helyezze be a klónozott táblázatot a dokumentumba az eredeti után
table.ParentNode.InsertAfter(tableClone, table);

// Szúrjon be egy üres bekezdést a két táblázat közé
// Ellenkező esetben mentéskor egyesítik őket (ez a dokumentum érvényesítéséből adódik)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Itt használjuk a`Clone` módszert a tömb teljes másolatának létrehozásához. Akkor használjuk`InsertAfter` a klónozott táblázat beillesztéséhez a dokumentumba, az eredeti táblázat után. A két tábla közé egy üres bekezdést is adunk, hogy ne egyesüljenek mentéskor.

## 4. lépés: Mentse el a módosított dokumentumot
Végül el kell mentenünk a módosított dokumentumot a klónozott táblával. Használja a következő kódot:

```csharp
// Mentse el a módosított dokumentumot
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.
  
### Minta forráskód a Clone Complete Table-hoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Klónozza a táblázatot, és helyezze be a dokumentumba az eredeti után.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Szúrjon be egy üres bekezdést a két táblázat közé,
	// vagy különben összevonják őket a mentéskor, ami a dokumentum érvényesítésével kapcsolatos.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan klónozhatunk egy teljes táblázatot Word-dokumentumba az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C# kódot, programozottan klónozhatja a Word-dokumentumok táblázatait. Ez a funkció lehetővé teszi a tömbök speciális szükségleteinek megfelelő speciális manipulációk végrehajtását.