---
title: Az ázsiai bekezdésközök és behúzások módosítása a Word-dokumentumban
linktitle: Az ázsiai bekezdésközök és behúzások módosítása a Word-dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan módosíthatja az ázsiai bekezdésközöket és behúzásokat a Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
Ebben az oktatóanyagban végigvezetjük, hogyan módosíthatja az ázsiai bekezdések térközét és behúzását az Aspose.Words for .NET használatával. Kövesse az alábbi lépéseket a forráskód megértéséhez és a módosítások alkalmazásához.

## 1. lépés: A dokumentum betöltése

A kezdéshez adja meg a dokumentumok könyvtárát, és töltse be az ázsiai tipográfiát tartalmazó dokumentumot egy dokumentum objektumba. Itt van, hogyan:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## 2. lépés: A bekezdések térközének és behúzásának módosítása

Most módosítjuk az ázsiai dokumentum első bekezdésének szóközét és behúzását. Itt van, hogyan:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Frissítse a ParagrafusFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Frissítse a ParagrafusFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //Frissítse a ParagrafusFormat.FirstLineIndent
format.LineUnitBefore = 5; // Frissítse a ChapterFormat.SpaceBefore fájlt
format.LineUnitAfter = 10; // Frissítse a ParagrafusFormat.SpaceAfter fájlt
```

## 3. lépés: A dokumentum mentése

 A szövegbeviteli űrlapmező beszúrása után mentse a dokumentumot a kívánt helyre a gombbal`Save` módszer. Ügyeljen arra, hogy megadja a megfelelő fájl elérési utat:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Példa forráskód az ázsiai bekezdésközök és behúzások módosításához az Aspose.Words használatával .NET-hez

Íme az Aspose.Words for .NET ázsiai bekezdésköz és behúzása szerkesztése funkció teljes forráskódja:

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // A bekezdésforma.LeftIndent frissítésre kerül.
	format.CharacterUnitRightIndent = 10;      // A ParagrafusFormat.RightIndent frissítésre kerül.
	format.CharacterUnitFirstLineIndent = 20;  // ParagrafusFormat.FirstLineIndent frissítésre kerül.
	format.LineUnitBefore = 5;                 // A ParagrafusFormat.SpaceBefore frissítésre kerül
	format.LineUnitAfter = 10;                 // A ParagrafusFormat.SpaceAfter frissítésre kerül

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Ezzel a kóddal módosíthatja az ázsiai bekezdések térközét és behúzását az Aspose.Words for .NET használatával.

## Következtetés

 Ebben az oktatóanyagban megtanultuk, hogyan lehet módosítani egy ázsiai bekezdés térközét és behúzását az Aspose.Words for .NET használatával. A vonatkozó tulajdonságok módosításával a`ParagraphFormat`szabályozhatjuk az ázsiai bekezdések elrendezését és megjelenését egy Word dokumentumban. Ez a funkció hasznos az ázsiai karaktereket tartalmazó szöveg formázásának testreszabásához és a kívánt vizuális megjelenítés eléréséhez vegyes nyelvű tartalmú dokumentumokban.

### GYIK

#### K: Mit csinál az Aspose.Words for .NET "Ázsiai bekezdésközök és behúzások módosítása" funkciója?

V: Az Aspose.Words for .NET "Ázsiai bekezdésközök és behúzások módosítása" funkciója lehetővé teszi az ázsiai bekezdések térközeinek és behúzási tulajdonságainak módosítását egy Word-dokumentumban. A bekezdés elrendezésének és megjelenésének szabályozásához beállíthatja a bal és a jobb oldali behúzást, az első sor behúzását, az előtti és utáni szóközt.

#### K: Hogyan módosíthatom egy ázsiai bekezdés térközét és behúzását az Aspose.Words for .NET használatával?

 V: Egy ázsiai bekezdés térközének és behúzásának módosításához el kell érnie a`ParagraphFormat`bekezdését, és módosítsa a vonatkozó tulajdonságait. A megadott példakódban elérjük a dokumentum első bekezdését, és beállítjuk a`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , és`LineUnitAfter` tulajdonságokkal a távolság és a behúzás beállításához.

#### K: Alkalmazhatom ezeket a változtatásokat a dokumentum többi bekezdésére?

 V: Igen, ezeket a módosításokat a dokumentum többi bekezdésére is alkalmazhatja, ha hozzáfér a megfelelő bekezdésekhez`ParagraphFormat` tárgyakat. A példakód a dokumentum első bekezdését célozza meg, de a többi bekezdést is módosíthatja az index módosításával`Paragraphs` gyűjtemény, vagy más kritériumok segítségével válassza ki a kívánt bekezdéseket.