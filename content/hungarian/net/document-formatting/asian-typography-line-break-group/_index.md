---
title: Ázsiai tipográfiai sortörés csoport a Word dokumentumban
linktitle: Ázsiai tipográfiai sortörés csoport a Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan használhatja az ázsiai tipográfia sortörés csoportját Word dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/document-formatting/asian-typography-line-break-group/
---
Ebben az oktatóanyagban bemutatjuk, hogyan használhatja az ázsiai tipográfia sortörés csoportját a Word dokumentum funkciójában az Aspose.Words for .NET segítségével. Kövesse az alábbi lépéseket a forráskód megértéséhez és a formázási módosítások alkalmazásához.

## 1. lépés: A dokumentum betöltése

A kezdéshez adja meg a dokumentumok könyvtárát, és töltse be az ázsiai tipográfiát tartalmazó dokumentumot egy dokumentum objektumba. Itt van, hogyan:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## 2. lépés: Ázsiai tipográfia beállítása

Most konfiguráljuk a dokumentum első bekezdésének ázsiai tipográfiai beállításait. Itt van, hogyan:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## 3. lépés: A dokumentum mentése

 A szövegbeviteli űrlapmező beszúrása után mentse a dokumentumot a kívánt helyre a gombbal`Save` módszer. Ügyeljen arra, hogy megadja a megfelelő fájl elérési utat:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Példa forráskód az Asian Typography Line Break Group számára az Aspose.Words for .NET használatával

Íme az Asian Typography Line Break Group funkció teljes forráskódja az Aspose.Words for .NET-hez:

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Ezzel a kóddal ázsiai tipográfiai sortörési csoportot alkalmazhat az Aspose.Words for .NET használatával.

## Következtetés

 Ebben az oktatóanyagban megvizsgáltuk az Aspose.Words for .NET "ázsiai tipográfiai sortörés csoportja" funkcióját. Konfigurálásával a`FarEastLineBreakControl`, `WordWrap` , és`HangingPunctuation` tulajdonságai a`ParagraphFormat`, tudtuk szabályozni az ázsiai tipográfia sortörési viselkedését egy Word dokumentumban. Ez a funkció hasznos az ázsiai karakterek kezeléséhez, valamint a megfelelő sortörések és szótördelés biztosításához vegyes nyelvű tartalmú dokumentumokban.

### GYIK

#### K: Mi az "ázsiai tipográfiai sortörés csoport" szolgáltatása az Aspose.Words for .NET-ben?

V: Az Aspose.Words for .NET "Ázsiai tipográfiai sortörés csoportja" funkciója lehetővé teszi az ázsiai tipográfia sortörési viselkedésének szabályozását egy Word-dokumentumban. Pontosabban, ez befolyásolja a sorok törését és tördelését, amikor ázsiai karakterekkel foglalkozik a bekezdésekben.

#### K: Hogyan engedélyezhetem az "ázsiai tipográfiai sortörés csoportot" az Aspose.Words for .NET-ben?

 V: Az "ázsiai tipográfiai vonaltörés csoport" engedélyezéséhez konfigurálnia kell a`FarEastLineBreakControl`, `WordWrap` , és`HangingPunctuation` tulajdonságai a`ParagraphFormat` dokumentumának megfelelő bekezdése(i)hez. Beállítás`FarEastLineBreakControl` nak nek`false` biztosítja, hogy az ázsiai karaktereket a latin karakterekhez hasonlóan kezeljék a sortörés tekintetében.`WordWrap` állítva`true` lehetővé teszi a tördelést az ázsiai tipográfiához, és`HangingPunctuation` állítva`false` megakadályozza az írásjelek lógását az ázsiai szövegben.

#### K: Alkalmazhatom az "ázsiai tipográfiai sortörés csoportot" egy dokumentum bizonyos bekezdéseire?

V: Igen, alkalmazhatja az "Ázsiai tipográfiai sortörés csoport" beállításait egy Word-dokumentum adott bekezdéseire. A példakódban a beállítások a dokumentum első bekezdésére vonatkoznak. Szükség szerint módosíthatja a kódot más bekezdések célzásához, ha eléri azokat a következőn keresztül`Paragraphs` a dokumentum vonatkozó szakasz(ok) gyűjteménye.