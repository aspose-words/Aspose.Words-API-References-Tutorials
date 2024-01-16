---
title: Lebegő asztalpozíció
linktitle: Lebegő asztalpozíció
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan helyezhet el egy táblázatot lebegő pozícióban egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/floating-table-position/
---

Ebben az oktatóanyagban megtudjuk, hogyan lehet az Aspose.Words for .NET-et használni a táblázat lebegő pozícióba helyezésére egy Word-dokumentumban. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Ennek az oktatóanyagnak a végén programozottan szabályozhatja a lebegő táblázatok helyzetét és igazítását a Word-dokumentumokban.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum betöltése és a táblázat elérése
Szövegfeldolgozás elindításához a táblázattal be kell töltenünk az azt tartalmazó dokumentumot, és hozzá kell férnünk. Kovesd ezeket a lepeseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Hozzáférés a tömbhöz
Table table = doc.FirstSection.Body.Tables[0];
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára. Győződjön meg arról is, hogy a dokumentum tartalmaz egy táblázatot, amelyet lebegő helyzetben kell elhelyezni.

## 3. lépés: Az úszódeszka elhelyezése
Ezután a táblát lebegő pozícióba helyezzük az Aspose.Words for .NET által biztosított tulajdonságokkal. Használja a következő kódot:

```csharp
// Az úszóasztal elhelyezése
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Itt használjuk a`AbsoluteHorizontalDistance` tulajdonsággal beállíthatja a táblázat abszolút vízszintes távolságát az oldal bal szélétől. Mi is használjuk a`RelativeVerticalAlignment` tulajdonság a táblázat relatív függőleges igazításának beállításához a környező tartalomhoz.

## 4. lépés: Mentse el a módosított dokumentumot
Végül el kell mentenünk a módosított dokumentumot úgy, hogy a táblázat lebegő pozícióban legyen. Használja a következő kódot:

```csharp
// Mentse el a módosított dokumentumot
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.

### Minta forráskód a Floating Table Position-hoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan helyezzünk el egy táblázatot lebegő pozícióban egy Word-dokumentumban az Aspose.Words for .NET segítségével. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C# kódot, akkor programozottan szabályozhatja a Word dokumentumokban lévő lebegő táblázatok helyzetét és igazítását.