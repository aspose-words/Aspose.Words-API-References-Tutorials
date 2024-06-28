---
title: Osztott táblázat
linktitle: Osztott táblázat
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan oszthat fel egy táblázatot egy Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-tables/split-table/
---

Ebben az oktatóanyagban megtudjuk, hogyan lehet felosztani egy táblázatot egy Word-dokumentumban az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Ennek az oktatóanyagnak a végén feloszthat egy táblázatot egy bizonyos sorból a Word-dokumentumokban.

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

## 3. lépés: Az asztal felosztása
Ezután felosztjuk a táblázatot egy bizonyos sorból. Használja a következő kódot:

```csharp
// Szerezd meg az első táblázatot
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Annak a vonalnak a meghatározása, amelytől a táblázatot el kell osztani
Row row = firstTable.Rows[2];

// Hozzon létre egy új tárolót az osztott táblához
Table table = (Table)firstTable.Clone(false);

// Helyezze be a tartályt az eredeti táblázat után
firstTable.ParentNode.InsertAfter(table, firstTable);

// A táblázatok közötti távolság megtartásához adjon hozzá egy pufferbekezdést
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Sorok áthelyezése az eredeti táblából a felosztott táblába
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Itt a dokumentum segítségével lekérjük az első táblát a dokumentum csomópontjából. Ezután meghatározzuk azt a sort, amelyből a táblázatot fel akarjuk osztani, ebben a példában ez a harmadik sor (2. index). Ezután létrehozunk egy új tárolót az eredeti tábla klónozásával, majd beillesztjük az eredeti tábla mögé. Egy puffer bekezdést is hozzáadunk a két tábla közötti távolság megtartásához. Ezután sorokat mozgatunk az eredeti táblából a felosztott táblába egy do-while ciklussal, amíg el nem érjük a megadott sort.

## 4. lépés: Mentse el a módosított dokumentumot
Végül meg kell mentenünk a

  a felosztott táblával módosított dokumentum. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.

### Minta forráskód a Split Table-hoz az Aspose.Words for .NET használatával 

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// A harmadik sorban lévő táblázatot felosztjuk (beleértve).
Row row = firstTable.Rows[2];
// Hozzon létre egy új tárolót az osztott táblához.
Table table = (Table) firstTable.Clone(false);
// Helyezze be a tartályt az eredeti után.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Adjon hozzá egy puffer bekezdést, hogy biztosítsa a táblázatok egymástól való távolságát.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet felosztani egy táblázatot egy Word-dokumentumban az Aspose.Words for .NET használatával. Ha követi ezt a lépésről lépésre szóló útmutatót, és implementálja a mellékelt C# kódot, könnyedén szétválaszthatja a táblákat egy bizonyos sorból a Word-dokumentumokban.