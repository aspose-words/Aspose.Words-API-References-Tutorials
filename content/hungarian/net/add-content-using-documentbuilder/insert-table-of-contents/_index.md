---
title: Helyezze be a tartalomjegyzéket a Word dokumentumba
linktitle: Helyezze be a tartalomjegyzéket a Word dokumentumba
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be tartalomjegyzéket Word dokumentumokba az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/add-content-using-documentbuilder/insert-table-of-contents/
---
Ebből az átfogó oktatóanyagból megtudhatja, hogyan szúrhat be tartalomjegyzéket egy Word-dokumentumba az Aspose.Words for .NET segítségével. Végigvezetjük a folyamaton, és biztosítjuk a szükséges C# kódrészleteket. Az útmutató végére képes lesz létrehozni egy tartalomjegyzéket a megfelelő címsorokkal és oldalszámokkal.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Az Aspose.Words for .NET könyvtár telepítve van a rendszerére.

## 1. lépés: Hozzon létre egy új dokumentumot és DocumentBuildert
Kezdésként hozzon létre egy új dokumentumot a Document osztály használatával, és inicializáljon egy DocumentBuilder objektumot:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Helyezzen be egy tartalomjegyzéket
Ezután használja a DocumentBuilder osztály InsertTableOfContents metódusát a tartalomjegyzék beszúrásához. Adja meg a szükséges formázási beállításokat a metóduson belül:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## 3. lépés: Dokumentumtartalom hozzáadása
A tartalomjegyzék beszúrása után adja hozzá a dokumentum tényleges tartalmát. Állítsa be a megfelelő címsorstílusokat a StyleIdentifier segítségével:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## 4. lépés: Frissítse a tartalomjegyzéket
Az újonnan beillesztett tartalomjegyzék kezdetben üres lesz. A feltöltéshez frissítse a dokumentum mezőit:

```csharp
doc.UpdateFields();
```

## 5. lépés: Mentse el a dokumentumot
A tartalomjegyzék beszúrása és a mezők frissítése után mentse a dokumentumot fájlba a Dokumentum osztály Mentés metódusával:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Példa forráskódra a tartalomjegyzék beszúrásához az Aspose.Words használatával a .NET-hez
Íme a teljes forráskód egy tartalomjegyzék beszúrásához az Aspose.Words for .NET használatával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inicializálja a DocumentBuilder-t Document objektummal
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Tartalomjegyzék beszúrása
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Kezdje a dokumentum tényleges tartalmát a második oldalon.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// Az újonnan beillesztett tartalomjegyzék kezdetben üres lesz.
// Ezt a dokumentum mezőinek frissítésével kell kitölteni.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan lehet tartalomjegyzéket beszúrni egy Word-dokumentumba az Aspose.Words for .NET segítségével. Ha követi ezt a lépésről lépésre szóló útmutatót, és felhasználja a mellékelt forráskódot, akkor most létrehozhat egy tartalomjegyzéket a megfelelő címsorokkal és oldalszámokkal a dokumentumokhoz.

### GYIK a tartalomjegyzék Word dokumentumba történő beillesztéséhez

#### K: Testreszabhatom a tartalomjegyzék megjelenését?

 V: Igen, testreszabhatja a tartalomjegyzék megjelenését a -ban megadott formázási beállítások módosításával`InsertTableOfContents` módszer. A paraméterek lehetővé teszik az oldalszámok, a behúzás és egyéb stílusok szabályozását.

#### K: Mi a teendő, ha bizonyos címsorszinteket szeretnék felvenni a tartalomjegyzékbe?

 V: Megadhatja a kívánt címsorszinteket, amelyek a tartalomjegyzékbe kerüljenek, ha módosítja az értéket a -n belül`InsertTableOfContents` módszer. Például a használatával`"\\o \"1-3\""` tartalmazni fogja az 1–3.

#### K: Frissíthetem automatikusan a tartalomjegyzéket, ha módosítom a dokumentum tartalmát?

 V: Igen, a tartalomjegyzéket automatikusan frissítheti a telefonszám hívásával`UpdateFields` módszer a dokumentumon. Ez biztosítja, hogy a dokumentum tartalmán végrehajtott változtatások, például a címsorok hozzáadása vagy eltávolítása megjelenjen a tartalomjegyzékben.

#### K: Hogyan alakíthatom másképp a tartalomjegyzék címsorszintjeit?

 V: A címsorszinteket eltérő stílusban adhatja meg, ha minden címsorszinthez különböző bekezdésstílust használ. Más hozzárendelésével`StyleIdentifier` értékeket a`ParagraphFormat` a`DocumentBuilder`, minden címsorszinthez külön stílust hozhat létre.

#### K: Lehetséges-e további formázást hozzáadni a tartalomjegyzék címsoraihoz?

 V: Igen, a tartalomjegyzék címsoraihoz további formázást is hozzáadhat, például betűstílusokat, színeket vagy egyéb tulajdonságokat. Beállításával a`Font` tulajdonságai a`DocumentBuilder`, egyéni formázást alkalmazhat a címsorokon.