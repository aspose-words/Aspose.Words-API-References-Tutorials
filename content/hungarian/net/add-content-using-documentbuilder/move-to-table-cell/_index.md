---
title: Mozgás táblázatcellába a Word dokumentumban
linktitle: Mozgás táblázatcellába a Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a Move To Table Cell használatához az Aspose.Words for .NET Word dokumentum funkciójában
type: docs
weight: 10
url: /hu/net/add-content-using-documentbuilder/move-to-table-cell/
---
Ebben a példában lépésről lépésre végigvezetjük az Aspose.Words for .NET Word dokumentumban az Áthelyezés táblázatcellába funkciójának használatán a mellékelt C# forráskód használatával. Ez a funkció lehetővé teszi, hogy egy Word-dokumentum táblázatában meghatározott cellákban navigáljon és kezeljen. Kövesse az alábbi lépéseket, hogy integrálja ezt a funkciót az alkalmazásba.

## 1. lépés: Töltse be a táblázatot tartalmazó dokumentumot

Először is be kell töltenünk azt a dokumentumot, amely azt a táblázatot tartalmazza, amelybe a cellát át akarjuk helyezni. A lépés végrehajtásához használja a következő kódot:

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

Ez a kód betölti a megadott dokumentumot (a "MyDir + "Tables.docx"" a táblázatot tartalmazó dokumentum tényleges elérési útjával).

## 2. lépés: Helyezze át a DocumentBuildert egy adott táblázatcellába

Ezután áthelyezzük a DocumentBuildert egy adott táblázatcellába. A lépés végrehajtásához használja a következő kódot:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

Ez a kód létrehoz egy DocumentBuilder-t a meglévő dokumentumból, majd áthelyezi a kurzort a DocumentBuilderből a megadott táblázatcellába. Végül a DocumentBuilder segítségével tartalmat ad hozzá a cellához`Write()` módszer.

## 3. lépés: Ellenőrizze az eredményt

Most ellenőrizheti, hogy a táblázatcellába való áthelyezés sikeres volt-e. A lépés végrehajtásához használja a következő kódot:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

Ez a kód ellenőrzi, hogy a megadott cella valóban a DocumentBuilder aktuális cellája. Azt is ellenőrzi, hogy a DocumentBuilder által hozzáadott tartalom megfelelően lett-e elmentve a táblázatcellában.

Ez minden ! Most már megértette, hogyan használhatja az Aspose.Words for .NET táblacellába költözésének funkcióját a megadott forráskód használatával. Most már integrálhatja ezt a funkciót saját alkalmazásaiba, és kezelheti a Word-dokumentumok egyes táblázatcelláit.


### Példa forráskódra a táblázatcellába való áthelyezéshez az Aspose.Words for .NET használatával


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Helyezze az építőt az első táblázat 3. sorába, 4. cellájába.
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

## Következtetés

Ebben a példában megvizsgáltuk az Aspose.Words for .NET Move To Table Cell funkcióját. Megtanultuk, hogyan tölthet be egy táblázatot tartalmazó dokumentumot, hogyan helyezheti át a DocumentBuildert egy adott táblázatcellába, és hogyan adhat hozzá tartalmat a cellához. Ez a szolgáltatás hatékony eszközöket biztosít a fejlesztők számára, hogy az Aspose.Words for .NET segítségével programozottan navigálhassanak és kezelhessenek bizonyos cellákat a Word dokumentumtáblázataiban. Értékes kiegészítője lehet a dinamikus Word-dokumentum-feldolgozáshoz és a táblázattartalom-kezeléshez.

### GYIK a Word dokumentum táblázatcellájába való áthelyezéshez

#### K: Mi a célja az Aspose.Words for .NET Move To Table Cell funkciójának?

V: Az Aspose.Words for .NET alkalmazás Move To Table Cell funkciója lehetővé teszi a fejlesztők számára, hogy programozottan navigáljanak egy Word-dokumentum táblázatában, és kezeljék azokat. Lehetővé teszi tartalom beszúrását, módosítását vagy törlését egy adott cellán belül.

#### K: Hogyan helyezhetem át a DocumentBuildert egy adott táblázatcellába egy Word-dokumentumban?

V: A DocumentBuilder áthelyezéséhez egy adott táblacellába egy Word dokumentumban, használhatja a DocumentBuilder osztály MoveToCell metódusát. Ez a módszer a táblázatban a célsor és -cella indexeit veszi paraméterként, és a kurzort a cella elejére helyezi.

#### K: Hozzáadhatok vagy módosíthatok tartalmat egy adott táblázatcellába való áthelyezés után az Áthelyezés táblázatcellába funkcióval?

V: Igen, ha a DocumentBuilder a MoveToCell segítségével a kívánt táblázatcellába került, a DocumentBuilder osztály különféle módszereivel, például Write, Writeln vagy InsertHtml használatával hozzáadhatja vagy módosíthatja a cella tartalmát.

#### K: Hogyan ellenőrizhetem, hogy a táblázatcellába való áthelyezés sikeres volt?

V: A táblázatcellába való sikeres áthelyezést a DocumentBuilder kurzorának ellenőrzésével ellenőrizheti. Összehasonlíthatja például a DocumentBuilder aktuális csomópontját azzal a cellával, amelybe át akart helyezni, és ellenőrizheti, hogy a DocumentBuilder által hozzáadott tartalom megfelelően van-e mentve a táblázatcellában.