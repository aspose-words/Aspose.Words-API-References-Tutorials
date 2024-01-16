---
title: Lista újraindítása minden szakasznál
linktitle: Lista újraindítása minden szakasznál
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthat vissza számozott listát a Word-dokumentum egyes szakaszaihoz az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-list/restart-list-at-each-section/
---

Ebben a lépésről lépésre bemutatott oktatóanyagban bemutatjuk, hogyan állíthat vissza számozott listát a Word-dokumentum egyes szakaszaihoz az Aspose.Words for .NET használatával. Elmagyarázzuk a mellékelt C# forráskódot, és megmutatjuk, hogyan implementálhatja azt saját projektjeibe.

 A kezdéshez győződjön meg arról, hogy az Aspose.Words for .NET telepítve van és konfigurálva van a fejlesztői környezetben. Ha még nem tette meg, töltse le és telepítse a könyvtárat innen[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1. lépés: A dokumentum és a lista létrehozása

Először hozzon létre egy új dokumentumot, és adjon hozzá egy alapértelmezett számozott listát:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## 2. lépés: Elemek hozzáadása a listához

 Ezután használja a`DocumentBuilder` elemek hozzáadásához a listához. Egy hurok segítségével több elemet is hozzáadhat a listához:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

Ebben a példában egy szakasztörést szúrunk be a 15. listaelem után az újraszámozás szemléltetésére.

## 3. lépés: Mentse el a módosított dokumentumot

Végül mentse el a módosított dokumentumot:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Így ! Sikeresen visszaállította a számozott listát a Word-dokumentum egyes szakaszaihoz az Aspose.Words for .NET használatával.

### Példa forráskódra a lista alaphelyzetbe állításához az egyes szakaszokban

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

Nyugodtan használhatja ezt a kódot saját projektjeiben, és módosíthatja sajátos igényei szerint.

### GYIK

#### K: Hogyan indíthatok újra egy listát az Aspose.Words minden szakaszában?

 V: Ha újra szeretné indítani a listát az Aspose.Words minden szakaszában, létre kell hoznia egy példányt a`List` osztályt, és rendeljünk hozzá egy számozott listát. Ezután használhatja a`List.IsRestartAtEachSection` tulajdonság megadásához, hogy a számozást minden szakasznál újra kell kezdeni. Ezt a listát a dokumentum egy vagy több részéhez társíthatja, így a számozás minden szakasznál helyesen indul újra.

#### K: Testreszabhatom az Aspose.Words listák számozási formátumát?

V: Igen, testreszabhatja a listák számozási formátumát az Aspose.Words-ben. A`List` osztály több tulajdonságot kínál erre, mint pl`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`, stb. Ezekkel a tulajdonságokkal beállíthatja a lista típusát (számozott, felsorolásjeles stb.), a számozási formátumot (arab számok, római számok, betűk stb.) és más számozási formázási beállításokat.

#### K: Lehetséges-e további szinteket hozzáadni az Aspose.Words számozott listájához?

 V: Igen, lehetséges további szinteket hozzáadni az Aspose.Words számozott listájához. A`ListLevel` osztály lehetővé teszi a formázási tulajdonságok beállítását a lista minden szintjéhez. Beállíthat olyan beállításokat, mint az előtag, utótag, igazítás, behúzás stb. Ez lehetővé teszi több szintű hierarchiával rendelkező listák létrehozását.