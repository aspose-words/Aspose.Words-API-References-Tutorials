---
title: Módosítsa a Toc tabulátorokat a Word dokumentumban
linktitle: Módosítsa a Toc tabulátorokat a Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan módosíthatja a tartalomjegyzék lapjait egy Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-table-of-content/change-toc-tab-stops/
---
Az Aspose.Words for .NET egy hatékony könyvtár Word dokumentumok létrehozásához, szerkesztéséhez és kezeléséhez C# alkalmazásokban. Az Aspose.Words által kínált funkciók között lehetőség van a Word-dokumentumok tartalomjegyzékében használt fülek módosítására. Ebben az útmutatóban bemutatjuk, hogyan használhatja az Aspose.Words for .NET C# forráskódját a dokumentum tartalomjegyzékének lapjainak megváltoztatásához.

## Az Aspose.Words könyvtár megértése

Mielőtt belemerülne a kódba, fontos megérteni a .NET Aspose.Words könyvtárát. Az Aspose.Words egy népszerű könyvtár, amely egyszerűvé és hatékonysá teszi a Word-dokumentumokkal végzett szövegfeldolgozást. A funkciók széles skáláját kínálja a Word-dokumentumok létrehozásához, szerkesztéséhez és kezeléséhez, beleértve a tartalomjegyzék lapok megváltoztatását.

## A tartalomjegyzéket tartalmazó dokumentum betöltése

Az első lépés a módosítani kívánt tartalomjegyzéket tartalmazó Word dokumentum betöltése. A Dokumentum osztály segítségével töltse be a dokumentumot a forrásfájlból. Íme egy példa:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Ebben a példában a dokumentumok könyvtárában található "Table of Contents.docx" dokumentumot töltjük be.

## Fülek módosítása a tartalomjegyzékben

A dokumentum betöltése után végigmegyünk a dokumentum minden bekezdésén, és ellenőrizzük, hogy a tartalomjegyzék (TOC) eredménystílusai szerint formázták-e. Ha igen, akkor módosítjuk az oldalszámok igazításához használt tabulátorokat. Itt van, hogyan:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

Ebben a példában egy ciklust használunk a dokumentum egyes bekezdései közötti ciklusra. Ezután ellenőrizzük, hogy a bekezdés a tartalomjegyzék eredményének (TOC) stílusával van-e formázva. Ha igen, akkor elérjük az ebben a bekezdésben használt első lapot, és módosítjuk azt úgy, hogy eltávolítjuk a régi lapot, és hozzáadunk egy új lapot egy módosított pozícióval.

## Módosított dokumentum mentése

Miután elvégezte a szükséges módosításokat a tartalomjegyzék fülein, a módosított dokumentumot a Dokumentum osztály Mentés metódusával mentheti el. Íme egy példa:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Ebben a példában a módosított dokumentumot "WorkingWithTableOfContent.ChangeTocTabStops.docx" néven mentjük.

### Minta forráskód a "Tartalomjegyzék lapjainak szerkesztése" funkcióhoz az Aspose.Words for .NET segítségével

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a tartalomjegyzéket tartalmazó dokumentumot
Document doc = new Document(dataDir + "Table of contents.docx");

// Módosítsa a tartalomjegyzék füleit
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Mentse el a módosított dokumentumot
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Következtetés

Ebben az útmutatóban bemutattuk, hogyan használhatja az Aspose.Words for .NET alkalmazást a Word-dokumentumok tartalomjegyzékének lapjainak módosításához a mellékelt C# forráskód használatával. A megadott lépések követésével egyszerűen testreszabhatja a tartalomjegyzék lapjait a Word-dokumentumokban a C# alkalmazásban. Az Aspose.Words rendkívüli rugalmasságot és teljesítményt kínál a dokumentumok stílusával és formázásával való munkavégzéshez, lehetővé téve vonzó és professzionális Word-dokumentumok létrehozását.

### GYIK a toc tabulátorok megváltoztatásához a Word dokumentumban

#### K: Mi a célja az Aspose.Words for .NET "Toc Tab Stops In Word Document" funkciójának?

V: Az Aspose.Words for .NET "Toc tabulátorhelyek módosítása a Word-dokumentumban" funkciója lehetővé teszi a Word-dokumentumok tartalomjegyzékében használt tabulátorok módosítását. Lehetővé teszi az oldalszámok és a megfelelő címsorok igazítását és elhelyezését a tartalomjegyzékben.

#### K: Mi az Aspose.Words for .NET?

V: Az Aspose.Words for .NET egy hatékony könyvtár, amelyet Word-dokumentumokkal való szövegfeldolgozáshoz terveztek .NET-alkalmazásokban. Átfogó szolgáltatásokat biztosít Word dokumentumok létrehozásához, szerkesztéséhez, manipulálásához és programozott konvertálásához C# vagy más .NET nyelvek használatával.

#### K: Hogyan tölthetek be egy tartalomjegyzéket tartalmazó Word-dokumentumot az Aspose.Words for .NET használatával?

 V: A tartalomjegyzéket tartalmazó Word-dokumentum Aspose.Words for .NET használatával betöltéséhez használja a`Document` osztály és annak konstruktora. A dokumentum fájlútvonalának megadásával betöltheti a`Document` tárgy. Íme egy példa:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Ez a kódrészlet betölti a megadott könyvtárban található "Table of Contents.docx" dokumentumot.

#### K: Hogyan módosíthatom a tartalomjegyzékben használt füleket az Aspose.Words for .NET használatával?

 V: A dokumentum betöltése után ismételheti a dokumentum egyes bekezdéseit, és ellenőrizheti, hogy a tartalomjegyzék (TOC) eredménystílusai alapján formázták-e. Ha egy bekezdés TOC stílusban van formázva, módosíthatja az oldalszámok igazításához használt tabulátorokat. Az Aspose.Words for .NET alkalmazásban elérheti a`ParagraphFormat` minden bekezdés tulajdonsága a tabulátorok lekéréséhez és módosításához. Íme egy példa:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        TabStop tab = para.ParagraphFormat.TabStops[0];
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }
}
```

Ebben a kódban a ciklus a dokumentum minden bekezdésén keresztül iterál. Ha egy bekezdés TOC-stílusú, akkor hozzáfér az adott bekezdésben használt első tabulátorhoz, eltávolítja azt, és új tabulátort ad hozzá egy módosított pozícióval.

#### K: Módosíthatom a lapokat a tartalomjegyzék több szintjéhez az Aspose.Words for .NET használatával?

V: Igen, a tartalomjegyzék több szintjén módosíthatja a lapokat az Aspose.Words for .NET használatával. Az egyes bekezdések megismétlésével és a tartalomjegyzék stílusának ellenőrzésével az egyes szintek lapjait külön-külön módosíthatja. Elérheti a tartalomjegyzék kívánt szintjét, és ennek megfelelően állíthatja be a tabulátorokat.

#### K: Hogyan menthetem el a módosított dokumentumot, miután megváltoztattam a tartalomjegyzék füleit az Aspose.Words for .NET használatával?

 V: Miután elvégezte a szükséges módosításokat a tartalomjegyzék fülein, a módosított dokumentumot a`Save` módszere a`Document` osztály. Paraméterként adja meg a kimeneti dokumentum kívánt fájl elérési útját és nevét`Save` módszer. Íme egy példa:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Ez a kód "WorkingWithTableOfContent.ChangeTocTabStops.docx" néven menti a módosított dokumentumot.

#### K: Testreszabhatom a tartalomjegyzék egyéb szempontjait az Aspose.Words for .NET használatával?

V: Igen, az Aspose.Words for .NET segítségével testreszabhatja a tartalomjegyzék különböző aspektusait. A fülek módosításán kívül módosíthatja a tartalomjegyzék-bejegyzések és oldalszámok betűstílusait, méretét, igazítását és egyéb formázási tulajdonságait. Ezenkívül beállíthatja a megfelelő címsorok behúzását, térközét és formázását.

#### K:. Módosíthatom a tartalomjegyzék tabulátor-igazítását és vezetőkaraktereit az Aspose.Words for .NET használatával?

V: Igen, módosíthatja a tartalomjegyzék tabulátor-igazítását és vezetőkaraktereit az Aspose.Words for .NET segítségével. A tabulátorok elérésével, valamint igazítási és vezetői tulajdonságaik beállításával szabályozhatja az oldalszámok és a megfelelő címsorok igazítását és vizuális megjelenését a tartalomjegyzékben.

#### K: Az Aspose.Words for .NET támogatja más stílusok és formázások megváltoztatását a Word dokumentumokban?

V: Igen, az Aspose.Words for .NET széleskörű támogatást nyújt a Word dokumentumok különböző stílusainak és formázásainak megváltoztatásához. Lehetővé teszi a különböző elemek, például bekezdések, címsorok, táblázatok, listák és egyebek stílusának módosítását. Igényeinek megfelelően módosíthatja a betűtípusokat, a színeket, az igazítást, a behúzást, a térközt és egyéb formázási szempontokat.

#### K: Módosíthatom egy meglévő Word-dokumentum tartalomjegyzékének füleit az Aspose.Words for .NET használatával?

V: Igen, módosíthatja a tartalomjegyzék füleit egy meglévő Word-dokumentumban az Aspose.Words for .NET használatával. A dokumentum betöltésével, a bekezdések ismétlésével és a tabulátorok szükséges módosításával frissítheti a tartalomjegyzék füleit. Végül mentse el a dokumentumot a módosítások alkalmazásához.