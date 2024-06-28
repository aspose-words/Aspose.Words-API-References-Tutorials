---
title: Indítsa újra a lista számát
linktitle: Indítsa újra a lista számát
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthatja vissza a listák számát egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-list/restart-list-number/
---
Ebben a lépésenkénti oktatóanyagban bemutatjuk, hogyan állíthatja vissza a listák számát egy Word-dokumentumban az Aspose.Words for .NET használatával. Elmagyarázzuk a mellékelt C# forráskódot, és megmutatjuk, hogyan implementálhatja azt saját projektjeibe.

 A kezdéshez győződjön meg arról, hogy az Aspose.Words for .NET telepítve van és konfigurálva van a fejlesztői környezetben. Ha még nem tette meg, töltse le és telepítse a könyvtárat innen[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1. lépés: A dokumentum és a dokumentumgenerátor létrehozása

Először hozzon létre egy új dokumentumot és egy kapcsolódó dokumentumgenerátort:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Az első lista létrehozása és testreszabása

Ezután hozzon létre egy listát egy meglévő sablon alapján, majd szabja testre a szintjeit:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## 3. lépés: Elemek hozzáadása az első listához

Használja a dokumentumkészítőt elemek hozzáadásához az első listához és listaszámok eltávolításához:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## 4. lépés: A második lista létrehozása és testreszabása

Ha újra szeretné használni az első listát a szám visszaállításával, hozzon létre egy másolatot az eredeti listaelrendezésről:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Szükség esetén további módosításokat is végezhet a második listán.

## 5. lépés: Elemek hozzáadása a második listához

Használja újra a dokumentumkészítőt elemek hozzáadásához a második listához, és távolítsa el a listaszámokat:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## 6. lépés: Mentse el a módosított dokumentumot

Végül mentse el a módosított dokumentumot:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Így ! Sikeresen visszaállította egy lista számát egy Word-dokumentumban az Aspose.Words for .NET használatával.

### Minta forráskód a listaszám visszaállításához

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Hozzon létre egy listát egy sablon alapján.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// Az első lista újrafelhasználásához újra kell indítanunk a számozást az eredeti listaformázás másolatának létrehozásával.
List list2 = doc.Lists.AddCopy(list1);

// Az új listát bármilyen módon módosíthatjuk, beleértve az új rajtszám beállítását is.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### GYIK

#### K: Hogyan indíthatom újra egy lista számozását az Aspose.Words-ben?

 V: Egy lista számozásának újraindításához az Aspose.Words programban használhatja a`ListRestartAtNumber` módszere a`List` osztály. Ez a módszer lehetővé teszi egy új tárcsázási érték beállítását, amelytől a listát újra kell indítani. Például használhatja`list.ListRestartAtNumber(1)` a számozás újraindításához 1-től.

#### K: Testreszabható az újraindított listaszámozás elő- és utótagja az Aspose.Words-ben?

 V: Igen, testreszabhatja az újraindított listaszámozás elő- és utótagját az Aspose.Words-ben. A`ListLevel` osztály olyan tulajdonságokat kínál, mint pl`ListLevel.NumberPrefix` és`ListLevel.NumberSuffix`amelyek lehetővé teszik az elő- és utótag megadását a lista minden szintjéhez. Ezekkel a tulajdonságokkal szükség szerint testreszabhatja az elő- és utótagot.

#### K: Hogyan adhatok meg egy adott számozási értéket, amelytől a listát újra kell indítani?

 V: Egy adott számérték megadásához, amelytől a listát újra kell indítani, használhatja a`ListRestartAtNumber` metódus, amely argumentumként adja át a kívánt értéket. Például a számozás 5-től való újraindításához használhatja`list.ListRestartAtNumber(5)`.

#### K: Lehetséges-e újraindítani a többszintű listaszámozást az Aspose.Words-ben?

 V: Igen, az Aspose.Words támogatja a több listaszint újraindítási számozását. Alkalmazhatja a`ListRestartAtNumber` módszert minden listaszinten a számozás egyéni újraindításához. Például használhatja`list.Levels[0].ListRestartAtNumber(1)` az első listaszint újraindításához 1-ről, és`list.Levels[1].ListRestartAtNumber(1)` a második szintű lista újraindításához 1-től kezdve, és így tovább.



