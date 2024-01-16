---
title: Szöveg figyelmen kívül hagyása a beszúrás verzióin belül
linktitle: Szöveg figyelmen kívül hagyása a beszúrás verzióin belül
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan használhatja az Aspose.Words for .NET "Szöveg figyelmen kívül hagyása a módosításokon belül" funkcióját a Word-dokumentumok beszúrási változatainak kezeléséhez.
type: docs
weight: 10
url: /hu/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

Ebben a cikkben megvizsgáljuk a fenti C# forráskódot, hogy megértsük, hogyan használható az Aspose.Words for .NET könyvtárban található Szöveg figyelmen kívül hagyása a változatok beszúrása funkciójában. Ez a funkció akkor hasznos, ha figyelmen kívül akarjuk hagyni a szöveg beszúrását a revíziókon belül a dokumentumok kezelése közben.

## Előfeltételek

- C# nyelv alapismerete.
- .NET fejlesztői környezet telepített Aspose.Words könyvtárral.

## 1. lépés: Új dokumentum létrehozása

 Mielőtt elkezdené manipulálni a szöveget a beillesztési változatokon belül, létre kell hoznunk egy új dokumentumot az Aspose.Words for .NET használatával. Ezt úgy lehet megtenni, hogy a`Document` tárgy:

```csharp
Document doc = new Document();
```

## 2. lépés: Szöveg beszúrása revíziókövetéssel

 Ha megvan a dokumentumunk, a revíziókövetéssel ellátott szöveget a segítségével szúrhatjuk be`DocumentBuilder`tárgy. Például a "Beszúrva" szöveg beszúrásához revíziókövetéssel használhatjuk a`StartTrackRevisions`, `Writeln` és`StopTrackRevisions` mód:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## 3. lépés: Szúrjon be nem ellenőrzött szöveget

 A revíziókövetéssel rendelkező szövegek mellett a felülvizsgálatlan szöveget is beszúrhatjuk a`DocumentBuilder` tárgy. Például a "Szöveg" szöveg átdolgozás nélküli beszúrásához használhatjuk a`Write` módszer:

```csharp
builder.Write("Text");
```

## 4. lépés: A Szöveg figyelmen kívül hagyása a változatok beszúrása funkcióban

 Ha figyelmen kívül szeretnénk hagyni a szöveget a beszúrási revíziókon belül a következő műveleteknél, használhatjuk a`FindReplaceOptions` objektumot és állítsa be a`IgnoreInserted`tulajdonát`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## 5. lépés: Reguláris kifejezések használata kereséshez és cseréhez

A dokumentumszöveg keresési műveleteinek és cseréjének végrehajtásához reguláris kifejezéseket használunk. Példánkban megkeressük az "e" betű összes előfordulását, és csillagra cseréljük őket* .NET-et fogunk használni`Regex` osztály ehhez:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## 6. lépés: A módosított dokumentum kimenet megtekintése

 A keresés és csere alkalmazása után a dokumentum megváltozott tartalmát a segítségével tudjuk megjeleníteni`GetText` módszer:

```csharp
Console.WriteLine(doc.GetText());
```

## 7. lépés: Módosítsa a beállításokat a beszúrási változatok felvételéhez

Ha a beszúrási revíziókon belüli szöveget bele akarjuk foglalni a kimeneti eredménybe, módosíthatjuk a beállításokat, hogy ne hagyjuk figyelmen kívül a beszúrási revíziókat. Ehhez beállítjuk a`IgnoreInserted`tulajdonát`false`:

```csharp
options.IgnoreInserted = false;
```

## 8. lépés: A módosított dokumentum megtekintése beszúrás-változatokkal

Az opciók megváltoztatása után végre tudjuk hajtani a keresést és a cserét, hogy az eredmény a beszúrási revíziókon belüli szöveggel kapjuk meg:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Példa forráskódra az Aspose.Words for .NET-hez való szövegbeszúráson belüli változatok figyelmen kívül hagyásához

Íme a teljes mintaforráskód, amely bemutatja a Szöveg figyelmen kívül hagyása a változatok beszúrása funkciójában az Aspose.Words for .NET-hez:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Szöveg beszúrása nyomon követési változatokkal.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Nem átdolgozott szöveg beszúrása.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## Következtetés

Ebben a cikkben megvizsgáltuk a C# forráskódot, hogy megértsük, hogyan használható az Aspose.Words for .NET verzióiban a szöveg figyelmen kívül hagyása funkciója. Lépésenkénti útmutatót követtünk a dokumentum létrehozásához, a nyomkövető revíziókkal rendelkező szöveg beszúrásához és a nem felülvizsgált szöveghez, a Szöveg figyelmen kívül hagyása a változatok beszúrása funkció használatához, a keresési és csereműveletek végrehajtásához reguláris kifejezésekkel, valamint a módosított dokumentum megjelenítéséhez.

### GYIK

#### K: Mi az Aspose.Words for .NET "Szöveg figyelmen kívül hagyása a módosításokon belül" funkciója?

V: Az Aspose.Words for .NET "Szöveg figyelmen kívül hagyása a beszúráson belüli változatokon" funkciója lehetővé teszi annak megadását, hogy a beszúráson belüli szöveget figyelmen kívül kell-e hagyni bizonyos műveletek során, például szöveg keresése és cseréje során. Ha ez a funkció engedélyezve van, a beillesztési változatokban lévő szöveget a rendszer nem veszi figyelembe a műveletek során.

#### K: Hogyan hozhatok létre új dokumentumot az Aspose.Words for .NET használatával?

 V: Ha új dokumentumot szeretne létrehozni az Aspose.Words for .NET használatával, példányosíthat egy`Document` tárgy. Íme egy példa a C# kódra új dokumentum létrehozásához:

```csharp
Document doc = new Document();
```

#### K: Hogyan szúrhatok be szöveget revíziókövetéssel az Aspose.Words for .NET-be?

V: Ha már rendelkezik egy dokumentummal, akkor az a segítségével beszúrhat szöveget revíziókövetéssel`DocumentBuilder` tárgy. Például a "Beszúrva" szöveg beszúrásához revíziókövetéssel, használhatja a`StartTrackRevisions`, `Writeln` , és`StopTrackRevisions` mód:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### K: Hogyan illeszthetek be felül nem vizsgált szöveget az Aspose.Words for .NET-be?

 V: A revíziókövetéssel rendelkező szövegen kívül felülvizsgálatlan szöveget is beszúrhat a segítségével`DocumentBuilder` tárgy. Például a "Szöveg" szöveg átdolgozás nélküli beszúrásához használhatja a`Write` módszer:

```csharp
builder.Write("Text");
```

#### K: Hogyan hagyhatom figyelmen kívül a szöveget az Aspose.Words for .NET beszúrásain belül?

 V: Ha a későbbi műveletek során figyelmen kívül szeretné hagyni a szöveg beszúrási változatait, használhatja a`FindReplaceOptions` objektumot és állítsa be a`IgnoreInserted`tulajdonát`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### K: Hogyan hajthatok végre keresést és cserét reguláris kifejezések használatával az Aspose.Words for .NET-ben?

 V: Ha keresési és csereműveleteket szeretne végrehajtani a dokumentum szövegén reguláris kifejezések használatával, használhatja a .NET-et`Regex` osztály. Például megkeresheti az "e" betű összes előfordulását, és csillaggal helyettesítheti őket* ", létrehozhat a`Regex` objektumot, és használja a`Replace` módszer:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### K: Hogyan tekinthetem meg a dokumentum módosított kimenetét az Aspose.Words for .NET-ben?

 V: A keresés és csere műveletek alkalmazása után megtekintheti a dokumentum megváltozott tartalmát a segítségével`GetText` módszer:

```csharp
Console.WriteLine(doc.GetText());
```

#### K: Hogyan foglalhatom bele a beillesztési változatokat az Aspose.Words for .NET kimeneti eredményébe?

 V: Ha a kimeneti eredménybe bele szeretné foglalni a szöveg beszúrási változatait, módosíthatja a beállításokat, hogy ne hagyja figyelmen kívül a beszúrási változatokat. Ehhez beállíthatja a`IgnoreInserted` tulajdona a`FindReplaceOptions` tiltakozni`false`:

```csharp
options.IgnoreInserted = false;
```

#### K: Hogyan jeleníthetem meg a módosított dokumentumot az Aspose.Words for .NET beszúrási változataival?

V: Miután módosította a beillesztési revíziók felvételére vonatkozó beállításokat, végrehajthatja a keresést és a cserét újra, hogy az eredmény a beszúrási revíziókon belüli szöveggel jelenjen meg:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```