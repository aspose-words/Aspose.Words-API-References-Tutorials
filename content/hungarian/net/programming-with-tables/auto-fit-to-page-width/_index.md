---
title: Automatikus igazítás az oldal szélességéhez
linktitle: Automatikus igazítás az oldal szélességéhez
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan igazíthat automatikusan egy táblázatot az oldalszélességhez egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/auto-fit-to-page-width/
---

Ebben az oktatóanyagban megtanuljuk, hogyan használhatja az Aspose.Words for .NET alkalmazást a táblázat automatikus, oldalszélességéhez igazításához egy Word-dokumentumban. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Ennek az oktatóanyagnak a végén képes lesz programozottan kezelni a Word dokumentumok táblázatait.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum létrehozása és konfigurálása
Words Processing táblával való elindításához létre kell hoznunk egy dokumentumot, és be kell állítani a dokumentumgenerátort. Kovesd ezeket a lepeseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozd létre a dokumentumot és a dokumentumgenerátort
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 3. lépés: A táblázat beszúrása és konfigurálása
Ezután beszúrunk egy táblázatot a dokumentumba, amelynek szélessége az oldal szélességének felét foglalja el. Használja a következő kódot:

```csharp
// Helyezze be a táblázatot, és állítsa be a szélességét
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Itt a dokumentumkészítővel elindítjuk a táblázat létrehozását, beszúrjuk a cellákat, és beállítjuk a táblázat kívánt szélességét az oldal szélességének 50%-ára. Ezután minden cellába szöveget adunk.

## 4. lépés: Mentse el a módosított dokumentumot
Végül el kell mentenünk a módosított dokumentumot az oldal szélességéhez igazított táblázattal. Használja a következő kódot:

```csharp
// Mentse el a módosított dokumentumot
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.
  
### Minta forráskód az automatikus oldalszélességhez igazításhoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Szúrjon be egy olyan táblázatot, amely az oldal szélességének felét foglalja el.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet automatikusan egy táblázatot az oldalszélességhez igazítani egy Word-dokumentumban az Aspose.Words for .NET használatával. Ha követi ezt a lépésről lépésre szóló útmutatót, és implementálja a mellékelt C# kódot, akkor programozottan kezelheti a Word-dokumentumokban lévő táblázatokat. Ez a funkció lehetővé teszi a táblázat szélességének dinamikus igazítását az oldalnak megfelelően, így professzionális és látványos dokumentumot kínál.