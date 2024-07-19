---
title: A Word-dokumentum felosztása címsorok szerint HTML
linktitle: Címsorok Html szerint
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre az Aspose.Words for .NET HTML-szolgáltatásának fejlécével a felosztott Word-dokumentum C# forráskódjának magyarázatához
type: docs
weight: 10
url: /hu/net/split-document/by-headings-html/
---
Ebben az oktatóanyagban végigvezetjük, hogyan oszthat fel egy Word-dokumentumot kisebb részekre az Aspose.Words for .NET HTML-címsor alapján funkciójával. Kövesse az alábbi lépéseket a forráskód megértéséhez, és külön HTML dokumentumok létrehozásához a címsor alapján.

## 1. lépés: A dokumentum betöltése

A kezdéshez adja meg a dokumentum könyvtárát, és töltse be a dokumentumot egy dokumentum objektumba. Itt van, hogyan:

```csharp
// dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## 2. lépés: A dokumentum felosztása címsor szerint HTML formátumban

Most beállítjuk a mentési beállításokat, hogy a dokumentumot kisebb részekre oszthassuk a Címsor alapján HTML formátumban. Itt van, hogyan:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Ossza fel a dokumentumot kisebb részekre, ebben az esetben válassza el cím szerint.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Példa forráskódra a By Headings HTML-hez az Aspose.Words for .NET használatával

Íme az Aspose.Words for .NET HTML címsor alapján funkciójának teljes forráskódja:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// A dokumentum felosztása kisebb részekre, ebben az esetben fejléc szerint.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Ezzel a kóddal egy Word-dokumentumot kisebb részekre bonthat az Aspose.Words for .NET használatával, címsorok alapján. Ezután minden részhez külön HTML dokumentumokat hozhat létre.

## Következtetés

 Ebben az oktatóanyagban megtanultuk, hogyan lehet egy Word-dokumentumot kisebb részekre osztani az Aspose.Words for .NET HTML-címsor alapján funkciójával. Megadva a`DocumentSplitCriteria` mint`HeadingParagraph` ban,-ben`HtmlSaveOptions`, külön HTML dokumentumokat tudtunk generálni az eredeti dokumentumban található fejlécek alapján.

A dokumentumok fejlécek szerinti felosztása hasznos lehet a tartalom rendszerezéséhez és kezeléséhez, különösen a több szakaszt tartalmazó nagy dokumentumok esetében. Az Aspose.Words for .NET megbízható és hatékony megoldást kínál a dokumentumok felosztására és különféle formátumú kimenetek előállítására.

Nyugodtan fedezze fel az Aspose.Words for .NET által biztosított további szolgáltatásokat és lehetőségeket, hogy tovább javítsa dokumentumfeldolgozási képességeit és egyszerűsítse a munkafolyamatot.

### GYIK

#### Hogyan oszthatok fel egy Word-dokumentumot kisebb részekre fejlécek alapján az Aspose.Words for .NET használatával?

 A Word-dokumentumok címsorok alapján történő felosztásához használhatja az Aspose.Words for .NET HTML-címsor alapján funkcióját. Kövesse a megadott forráskódot, és állítsa be a`DocumentSplitCriteria` nak nek`HeadingParagraph` ban,-ben`HtmlSaveOptions` tárgy. Ezzel a dokumentumot minden fejlécnél kisebb részekre osztja.

#### Milyen formátumokra oszthatom fel a Word dokumentumot?

 A mellékelt forráskód bemutatja a Word dokumentum kisebb részekre bontását HTML formátumban. Az Aspose.Words for .NET azonban különféle kimeneti formátumokat támogat, beleértve a DOCX, PDF, EPUB stb. Módosíthatja a kódot, és megadhatja a kívánt kimeneti formátumot a`HtmlSaveOptions` ennek megfelelően tiltakozik.

#### Választhatok-e más kritériumot a dokumentum felosztásához?

Igen, az igényeinek megfelelően választhat más kritériumot a dokumentum felosztásához. Az Aspose.Words for .NET számos kritériumlehetőséget biztosít, mint pl`HeadingParagraph`, `Page`, `Section` , és több. Módosítsa a`DocumentSplitCriteria` ingatlan a`HtmlSaveOptions` objektumot, hogy kiválassza a megfelelő kritériumokat a felosztáshoz.

#### Hogyan szabhatom testre a kimeneti HTML-t a felosztott részekhez?

 Az Aspose.Words for .NET lehetővé teszi a kimeneti HTML testreszabását a felosztott részek számára a további beállítások megadásával`HtmlSaveOptions` tárgy. Különféle szempontokat szabályozhat, például CSS-stílusokat, képeket, betűtípusokat és egyebeket. A HTML-kimenet testreszabásával kapcsolatos további részletekért tekintse meg az Aspose.Words dokumentációt.

#### Feloszthatom a dokumentumot több feltétel alapján?

 Igen, a dokumentumot több feltétel alapján is feloszthatja, ha a feltételeket ennek megfelelően kombinálja. Például feloszthatja a dokumentumot fejléc és oldal szerint is, ha beállítja a`DocumentSplitCriteria`tulajdonát`HeadingParagraph | Page`. Ez felosztja a dokumentumot az egyes fejléceknél és oldalakon, és mindkét kritérium alapján kisebb részeket hoz létre.