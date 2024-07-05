---
title: Tartsa együtt az asztalt
linktitle: Tartsa együtt az asztalt
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan tarthat össze egy táblázatot egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/keep-table-together/
---

Ebben az oktatóanyagban megtudjuk, hogyan lehet egy táblázatot összetartani egy Word-dokumentumban az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Ennek az oktatóanyagnak a végére képes lesz megőrizni a táblázatot érintetlenül anélkül, hogy az több oldalra osztódna a Word-dokumentumokban.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum betöltése és a táblázat előhívása
A Szövegfeldolgozás elindításához a táblázattal be kell töltenünk a dokumentumot, és le kell kérnünk a táblázatot, amelyet együtt szeretnénk tartani. Kovesd ezeket a lepeseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Vedd vissza az asztalt
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 3. lépés: Engedélyezze a „KeepWithNext” opciót
Annak érdekében, hogy a táblázat egyben maradjon, és ne váljon szét több oldalra, engedélyeznünk kell a "KeepWithNext" opciót a táblázat minden bekezdésénél, kivéve a táblázat utolsó sorának utolsó bekezdéseit. Használja a következő kódot:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Itt végigpörgetjük a táblázat minden celláját, és engedélyezzük a "KeepWithNext" opciót a cellában lévő minden egyes bekezdéshez, kivéve a táblázat utolsó sorának utolsó bekezdéseit.

## 4. lépés: Mentse el a módosított dokumentumot
Végül el kell mentenünk a módosított dokumentumot a táblázat összetartásával. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.

### Minta forráskód a Keep Table Together programhoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Engedélyeznünk kell a KeepWithNext funkciót a táblázat minden bekezdéséhez, hogy ne törjön át egy oldalon,
	// kivéve a táblázat utolsó sorának utolsó bekezdéseit.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet összetartani egy táblázatot egy Word-dokumentumban az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C#-kódot, megőrizheti a táblázat érintetlenségét, és megakadályozhatja, hogy a dokumentumokban több oldalra oszlana fel. Ezzel a funkcióval jobban szabályozhatja a dokumentumokban lévő táblázatok megjelenését és elrendezését.