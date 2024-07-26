---
title: Szerezzen lebegő asztali pozíciót
linktitle: Szerezzen lebegő asztali pozíciót
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan határozhatja meg a lebegő táblázatok pozícióját egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/get-floating-table-position/
---

Ebben az oktatóanyagban megtanuljuk, hogyan lehet lebegő táblázat helyzetét meghatározni egy Word-dokumentumban az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Ennek az oktatóanyagnak a végén programozottan megkaphatja a Word-dokumentumokban lévő lebegő táblázatok pozicionálási tulajdonságait.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum betöltése és a táblázatok elérése
A táblázatokkal történő szövegfeldolgozás elindításához be kell töltenünk az azokat tartalmazó dokumentumot, és el kell érnünk őket. Kovesd ezeket a lepeseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára. Győződjön meg arról is, hogy a dokumentum tartalmaz lebegő táblázatokat.

## 3. lépés: Lebegő asztalpozícionálási tulajdonságok lekérése
Ezután végigpörgetjük a dokumentum összes tábláját, és megkapjuk a lebegő táblázat pozicionálási tulajdonságait. Használja a következő kódot:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Ha a tömb lebegő típusú, akkor nyomtassa ki a pozicionálási tulajdonságait.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Itt használjuk a`foreach` hurok a dokumentum összes tömbjének ciklusához. Ellenőrizzük, hogy a tömb float típusú-e a`TextWrapping` ingatlan. Ha igen, akkor kinyomtatjuk a táblázat pozicionálási tulajdonságait, például vízszintes horgony, függőleges horgony, abszolút vízszintes és függőleges távolságok, átfedési engedély, abszolút vízszintes távolság és függőleges igazítási relatív.
 
### Minta forráskód a Lebegő táblázatpozíció lekéréséhez az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Ha a táblázat lebegő típusú, nyomtassa ki a pozicionálási tulajdonságait.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet lebegő táblázat helyzetét lekérni egy Word-dokumentumban az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C# kódot, akkor programozottan megkaphatja a Word dokumentumokban lévő lebegő táblázatok pozicionálási tulajdonságait. Ez a funkció lehetővé teszi a lebegő táblázatok elemzését és kezelését sajátos igényei szerint.