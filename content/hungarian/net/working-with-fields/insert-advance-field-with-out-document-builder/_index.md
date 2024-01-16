---
title: Előzetes mező beszúrása dokumentumkészítő nélkül
linktitle: Előzetes mező beszúrása dokumentumkészítő nélkül
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be speciális mezőket Word-dokumentumaiba az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Itt található egy lépésről lépésre bemutatott útmutató a C# forráskód leírásához, amely az Aspose.Words for .NET "Advanced Field Insertion without DocumentBuilder" funkcióját használja. A kívánt eredmény elérése érdekében gondosan kövesse az egyes lépéseket.

## 1. lépés: Dokumentumkönyvtár beállítása

A megadott kódban meg kell adnia dokumentumai könyvtárát. Cserélje le a „DOKUMENTUMKÖNYVTÁR” értéket a dokumentumkönyvtár megfelelő elérési útjára.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: A dokumentum és a bekezdés létrehozása

Kezdjük egy új dokumentum létrehozásával és az első bekezdés lekérésével.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 3. lépés: A speciális mező beszúrása

 Használjuk a`AppendField()` módszer egy speciális mező beillesztéséhez a bekezdésbe.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

Ezután a kívánt értékek megadásával konfiguráljuk a speciális mező különféle tulajdonságait.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 Végül hívjuk a`Update()` módszer a mező frissítéséhez.

```csharp
field. Update();
```

### Példa a forráskódra speciális mező beszúrásához DocumentBuilder nélkül az Aspose.Words for .NET-hez

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentumkészítés.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Adja meg a speciális mezőt.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

Ebben a példában létrehoztunk egy új dokumentumot, beszúrtunk egy speciális mezőt a DocumentBuilder használata nélkül, konfiguráltuk a különböző mezőtulajdonságokat, és elmentettük a dokumentumot egy megadott fájlnévvel.

Ezzel véget is értünk az „Insert Advanced Field Without DocumentBuilder” funkciónak az Aspose.Words for .NET-hez való használatáról szóló útmutatónknak.

### GYIK

#### K: Mi az Aspose.Words haladó területe?

V: Az Aspose.Words speciális mezője egy speciális mező, amely lehetővé teszi számítások elvégzését, feltételek beépítését és összetett műveletek végrehajtását egy Word-dokumentumban. Nagy rugalmasságot kínál dinamikus és egyéni mezők létrehozásához.

#### K: Hogyan lehet speciális mezőt beszúrni egy Word-dokumentumba az Aspose.Words dokumentumkészítőjének használata nélkül?

V: Ha speciális mezőt szeretne beszúrni egy Word-dokumentumba az Aspose.Words dokumentumkészítőjének használata nélkül, kövesse az alábbi lépéseket:

1. Importálja a dokumentumot és a mezőosztályt az Aspose.Words.Fields névtérből.
2. Hozzon létre egy példányt a dokumentumból a meglévő dokumentum betöltésével.
3. Használja az InsertField metódust speciális mező beszúrásához a speciális mezőkód megadásával.
4. Mentse el a dokumentumot.

#### K: Hogyan lehet egy speciális mező eredményét lekérni egy Word-dokumentumban?

V: Ha egy Word-dokumentum speciális mezőjének eredményét szeretné lekérni, használja a Mező osztályban elérhető Result tulajdonságot. Ez a tulajdonság a mező számított eredményét adja vissza.

#### K: Módosíthatom egy speciális mező képletét, miután beszúrtam egy Word dokumentumba?

V: Igen, szerkesztheti egy speciális mező képletét, miután beszúrta egy Word dokumentumba. Ezt úgy teheti meg, hogy eléri a Field osztály FieldCode tulajdonságát, és a képlet szövegének módosításával frissíti a képletet.