---
title: Szöveg figyelmen kívül hagyása a Változatok törlése alatt
linktitle: Szöveg figyelmen kívül hagyása a Változatok törlése alatt
second_title: Aspose.Words Document Processing API
description: Ismerje meg az Aspose.Words for .NET "Szöveg figyelmen kívül hagyása a változatok törlése közben" funkciójának használatát.
type: docs
weight: 10
url: /hu/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

Ebben a cikkben megvizsgáljuk a fenti C# forráskódot, hogy megértsük, hogyan használható az Aspose.Words for .NET könyvtár "Szöveg figyelmen kívül hagyása a változatok törlése alatt" funkciója. Ez a funkció akkor hasznos, ha figyelmen kívül akarjuk hagyni a szöveget a törlési revíziókon belül, amikor szövegfeldolgozást végez a dokumentumokkal.

## Az Aspose.Words for .NET könyvtár áttekintése

Mielőtt belemerülnénk a kód részleteibe, engedjék meg, hogy röviden bemutassam az Aspose.Words for .NET könyvtárat. Ez egy hatékony könyvtár, amely lehetővé teszi Word dokumentumok létrehozását, módosítását és konvertálását .NET alkalmazásokban. Számos fejlett funkciót kínál a dokumentumokkal végzett szövegfeldolgozáshoz, beleértve a revíziókezelést.

## A "Szöveg figyelmen kívül hagyása a változatok törlése alatt" funkció megértése

Az Aspose.Words for .NET "Szöveg figyelmen kívül hagyása a verzió törlésein belül" funkciója lehetővé teszi annak megadását, hogy a törlési változatokon belüli szöveget figyelmen kívül kell-e hagyni bizonyos műveletek során, például szöveg keresése és cseréje során. Ha ez a funkció engedélyezve van, a revíziókon belüli törölt szövegeket a rendszer nem veszi figyelembe a műveletek során.

## 1. lépés: Új dokumentum létrehozása az Aspose.Words for .NET használatával

 Mielőtt elkezdené manipulálni a szöveget egy dokumentumban, létre kell hoznunk egy új dokumentumot az Aspose.Words for .NET használatával. Megtehető az a. példányosításával`Document` tárgy:

```csharp
Document doc = new Document();
```

## 2. lépés: Nem felülvizsgált szöveg beszúrása a dokumentumba

 Ha megvan a dokumentumunk, az a segítségével beszúrhatunk még nem ellenőrzött szöveget`DocumentBuilder` tárgy. Például a "Törölt szöveg" szöveg beszúrásához használhatjuk a`Writeln` és`Write` mód:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## 3. lépés: Eltávolít egy bekezdést a módosítások nyomon követésével

"Szöveg figyelmen kívül hagyása a változatok törlése alatt" funkció használatának szemléltetésére a verziókövetéssel törölünk egy bekezdést a dokumentumból. Ez lehetővé teszi számunkra, hogy meglássuk, hogyan befolyásolja ez a funkció a későbbi műveleteket.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## 4. lépés: A "Szöveg figyelmen kívül hagyása a változatok törlése alatt" funkció alkalmazása

 Most, hogy elkészítettük dokumentumunkat egy bekezdés törlésével, egy`FindReplaceOptions` tárgy. Beállítjuk a`IgnoreDeleted`tulajdonát`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## 5. lépés: Reguláris kifejezések használata a kereséshez és a cseréhez

A dokumentum szövegén végzett keresési és csereműveletek végrehajtásához reguláris kifejezéseket használunk. Példánkban megkeressük az "e" betű összes előfordulását, és csillagra cseréljük őket* ". .HÁLÓ`Regex` osztályt használják erre:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## 6. lépés: A módosított dokumentum kimenet megjelenítése

 A keresés és csere alkalmazása után a dokumentum megváltozott tartalmát a segítségével tudjuk megjeleníteni`GetText` módszer:

```csharp
Console.WriteLine(doc.GetText());
```

## 7. lépés: Módosítsa a beállításokat a törölt szövegek felvételéhez

 Ha törölt szöveget szeretnénk belefoglalni a kimeneti eredménybe, módosíthatjuk a beállításokat, hogy ne hagyjuk figyelmen kívül a törölt szöveget. Ehhez beállítjuk a`IgnoreDeleted`tulajdonát`false`:

```csharp
options. IgnoreDeleted = false;
```

## 8. lépés: A módosított dokumentum kiadása törölt szöveggel

Az opciók módosítása után végre tudjuk hajtani a keresést és a cserét, hogy az eredményt a törölt szöveggel együtt kapjuk meg:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Példa forráskód az Aspose.Words for .NET-hez használt szöveg figyelmen kívül hagyása a törlésen belüli változatokhoz

Íme a teljes minta forráskód, amely bemutatja az Aspose.Words for .NET "Szöveg figyelmen kívül hagyása a módosításokon belül" funkciójának használatát:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Nem átdolgozott szöveg beszúrása.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Távolítsa el az első bekezdést a követési változatokkal.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## Következtetés

Ebben a cikkben megvizsgáltuk a C# forráskódot, hogy megértsük, hogyan használható az Aspose.Words for .NET "Szöveg figyelmen kívül hagyása a módosításokon belül" funkciójában. Ez a funkció akkor hasznos, ha a dokumentumok kezelésekor figyelmen kívül hagyja a törlési változatokon belüli szöveget. Lépésről lépésre követtük a dokumentum létrehozását, szöveg beszúrását, bekezdés törlését revíziókövetéssel, a "Szöveg figyelmen kívül hagyása a változatok törlése közben" funkciót, valamint keresési és csereműveleteket.

### GYIK

#### K: Mi az Aspose.Words for .NET "Szöveg figyelmen kívül hagyása a módosításokon belül" funkciója?

V: Az Aspose.Words for .NET "Szöveg figyelmen kívül hagyása a módosításokon belül" funkciója lehetővé teszi annak megadását, hogy a törlési változatokon belüli szöveget figyelmen kívül kell-e hagyni bizonyos műveletek során, például szöveg keresése és cseréje során. Ha ez a funkció engedélyezve van, a revíziókon belüli törölt szövegeket a rendszer nem veszi figyelembe a műveletek során.

#### K: Mi az Aspose.Words for .NET?

V: Az Aspose.Words for .NET egy hatékony könyvtár Word-dokumentumok létrehozására, szerkesztésére és .NET-alkalmazásokká való konvertálására. Számos fejlett funkciót kínál a dokumentumokkal végzett szövegfeldolgozáshoz, beleértve a revíziókezelést.

#### K: Hogyan lehet új dokumentumot létrehozni az Aspose.Words for .NET-ben?

 V: Mielőtt elkezdené manipulálni a szöveget egy dokumentumban, létre kell hoznia egy új dokumentumot az Aspose.Words for .NET használatával. Ezt úgy lehet megtenni, hogy a`Document` tárgy. Íme egy mintakód egy új dokumentum létrehozásához:

```csharp
Document doc = new Document();
```

#### K: Hogyan lehet szerkesztetlen szöveget beszúrni egy dokumentumba az Aspose.Words for .NET használatával?

 V: Ha már rendelkezik egy dokumentummal, az a segítségével beszúrhat még nem ellenőrzött szöveget`DocumentBuilder` tárgy. Például a "Törölt szöveg" szöveg beszúrásához használhatja a`Writeln` és`Write` mód:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### K: Hogyan törölhetek egy bekezdést az Aspose.Words for .NET-ben revíziókövetéssel?

V: A "Szöveg figyelmen kívül hagyása a változatok törlése alatt" funkció használatának szemléltetésére a felülvizsgálat követésével törölünk egy bekezdést a dokumentumból. Ez lehetővé teszi számunkra, hogy meglássuk, hogyan befolyásolja ez a funkció a további műveleteket.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### K: Hogyan lehet engedélyezni a "Szöveg figyelmen kívül hagyása a módosításokon belül" funkciót az Aspose.Words for .NET-ben?

 V: Most, hogy elkészítettük dokumentumunkat egy bekezdés törlésével, egy`FindReplaceOptions` tárgy. Beállítjuk a`IgnoreDeleted`tulajdonát`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### K: Hogyan lehet keresni és cserélni reguláris kifejezések használatával az Aspose.Words for .NET-ben?

V: A dokumentum szövegén végzett keresési és csereműveletek végrehajtásához reguláris kifejezéseket használunk. Példánkban megkeressük az "e" betű összes előfordulását, és csillagra cseréljük őket* A .NET-et fogjuk használni`Regex` osztály ehhez:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### K: Hogyan tekintheti meg a megváltozott dokumentumtartalmat az Aspose.Words for .NET-ben?

V: A keresés és csere alkalmazása után a dokumentum megváltozott tartalmát a segítségével tudjuk megjeleníteni`GetText` módszer:

```csharp
Console.WriteLine(doc.GetText());
```

#### K: Hogyan lehet törölt szöveget belefoglalni az Aspose.Words for .NET kimeneti eredményébe?

 V: Ha törölt szöveget szeretnénk belefoglalni a kimeneti eredménybe, módosíthatjuk a beállításokat, hogy ne hagyjuk figyelmen kívül a törölt szöveget. Ehhez beállítjuk a`IgnoreDeleted`tulajdonát`false`:

```csharp
options. IgnoreDeleted = false;
```

#### K: Hogyan lehet megjeleníteni a szerkesztett dokumentumot törölt szöveggel az Aspose.Words for .NET-ben?

V: Az opciók módosítása után új keresést végezhetünk, és lecserélhetjük, hogy az eredményt a törölt szöveggel kapjuk meg:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
