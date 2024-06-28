---
title: Alkalmazza a körvonalszegélyt
linktitle: Alkalmazza a körvonalszegélyt
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a körvonalkeret alkalmazásához egy táblázatban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük az Aspose.Words for .NET segítségével vázlatszegély alkalmazásának folyamatán. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Ennek az oktatóanyagnak a végére világosan megérti, hogyan kezelheti a Word-dokumentumok táblázatszegélyeit az Aspose.Words for .NET használatával.

## 1. lépés: Határozza meg a dokumentumkönyvtárat
Először is be kell állítania a dokumentumkönyvtár elérési útját. Ez az a hely, ahol a Word dokumentumot tárolják. Cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet a megfelelő elérési útra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Töltse fel a dokumentumot
 Ezután be kell töltenie a Word dokumentumot a`Document` osztály.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 3. lépés: Lépjen be az asztalhoz
 Vázlatszegély alkalmazásához el kell érnünk a dokumentumban található táblázatot. A`Table` osztály az Aspose.Words táblát képviseli.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## 4. lépés: Igazítsa a táblázatot az oldal közepéhez
 Most a táblázatot az oldal közepéhez igazíthatjuk a`Alignment` az asztal tulajdonsága.

```csharp
table. Alignment = Table Alignment. Center;
```

## 5. lépés: Törölje a meglévő táblázatszegélyeket.
Az új vázlatszegély használatához először törölnünk kell az összes meglévő szegélyt a táblázatból. Ezt a`ClearBorders()` módszer.

```csharp
table. ClearBorders();
```

## 6. lépés: Határozzon meg egy zöld szegélyt az asztal körül
 Most beállíthatunk egy zöld szegélyt az asztal körül a`SetBorder()` módszert a táblázat mindkét oldalára. Ebben a példában egy "Single" típusú szegélyt használunk, amelynek vastagsága 1,5 pont és zöld színű.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## 7. lépés: Töltse ki a cellákat háttérszínnel.
A táblázat vizuális megjelenítésének javítása érdekében a cellákat alapháttérszínnel is kitölthetjük.

ötlet. Ebben a példában világoszöld színt használunk.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## 8. lépés: Mentse el a módosított dokumentumot
Végül a módosított dokumentumot fájlba mentjük. Kiválaszthat egy megfelelő nevet és helyet a kimeneti dokumentumnak.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Gratulálok ! Az Aspose.Words for .NET segítségével vázlatszegélyt alkalmazott egy táblázatban.

### Minta forráskód az Apply Outline Border alkalmazáshoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Igazítsa a táblázatot az oldal közepéhez.
	table.Alignment = TableAlignment.Center;
	//Törölje a meglévő szegélyeket a táblázatból.
	table.ClearBorders();
	// Tegyél zöld szegélyt az asztal köré, de ne belül.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Töltsük fel a cellákat világoszöld egyszínű színnel.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan alkalmazhatunk körvonalszegélyt egy táblázatra az Aspose.Words for .NET használatával. Ennek a lépésről lépésre szóló útmutatónak a követésével könnyedén integrálhatja ezt a funkciót C#-projektjeibe. A táblázat formázásának manipulálása a dokumentumfeldolgozás alapvető eleme, és az Aspose.Words hatékony és rugalmas API-t kínál ennek eléréséhez. Ennek a tudásnak a birtokában javíthatja Word-dokumentumai vizuális megjelenítését, és megfelelhet bizonyos követelményeknek.