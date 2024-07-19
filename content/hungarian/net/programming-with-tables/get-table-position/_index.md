---
title: Szerezzen asztali pozíciót
linktitle: Szerezzen asztali pozíciót
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan határozhatja meg a táblázat pozícióját egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/get-table-position/
---

Ebben az oktatóanyagban megtudjuk, hogyan határozható meg egy táblázat pozíciója egy Word-dokumentumban az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Ennek az oktatóanyagnak a végén programozottan lekérheti a tábla pozicionálási tulajdonságait Word-dokumentumaiban.

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

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára. Győződjön meg arról is, hogy a dokumentum tartalmazza azt a táblázatot, amelynek pozícióját szeretné lekérni.

## 3. lépés: A tömb pozicionálási tulajdonságainak lekérése
Ezután ellenőrizzük a tömb pozicionálási típusát, és megkapjuk a megfelelő pozicionálási tulajdonságokat. Használja a következő kódot:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Itt egy feltételt használunk annak ellenőrzésére, hogy a tömb float típusú-e. Ha igen, kinyomtatjuk a`RelativeHorizontalAlignment`és`RelativeVerticalAlignment` tulajdonságokkal, hogy megkapja a táblázat relatív vízszintes és függőleges igazítását. Ellenkező esetben kinyomtatjuk a`Alignment` tulajdonság a tömb igazításának lekéréséhez.

### Minta forráskód a Táblázatpozíció lekéréséhez az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet lekérni egy táblázat pozícióját egy Word-dokumentumban az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C# kódot, akkor programozottan megkaphatja a táblapozícionálási tulajdonságokat a Word-dokumentumokban. Ez a funkció lehetővé teszi a tömbök elemzését és kezelését azok konkrét pozícióinak megfelelően.