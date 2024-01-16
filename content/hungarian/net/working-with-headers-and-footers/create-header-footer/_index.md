---
title: Hozzon létre fejléc láblécet
linktitle: Hozzon létre fejléc láblécet
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre fejlécet és láblécet Word-dokumentumaiban az Aspose.Words for .NET segítségével. Az egyes oldalak fejlécét és láblécét testreszabhatja.
type: docs
weight: 10
url: /hu/net/working-with-headers-and-footers/create-header-footer/
---

Íme egy lépésről lépésre bemutatott útmutató a következő C# forráskód leírásához, amellyel fejléceket és lábléceket hozhat létre az Aspose.Words for .NET funkcióval. A kód használata előtt győződjön meg arról, hogy az Aspose.Words könyvtárat belefoglalta a projektbe.

## 1. lépés: Állítsa be a dokumentumkönyvtár elérési útját

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Ügyeljen arra, hogy megadja a dokumentumkönyvtár megfelelő elérési útját, ahová a szerkesztett dokumentum mentésre kerül.

## 2. lépés: Hozzon létre egy dokumentumot és egy dokumentumgenerátort

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Itt létrehozunk egy példányt a`Document` osztály és egy példánya a`DocumentBuilder` osztály, amely lehetővé teszi számunkra a dokumentum kezelését és elemek hozzáadását.

## 3. lépés: Állítsa be az oldalparamétereket és az első fejlécet

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Adja meg, hogy az első oldal fejlécei/láblécei eltérjenek-e a többi oldaltól.
// A PageSetup.OddAndEvenPagesHeaderFooter tulajdonsággal is megadhatja
// különböző fejlécek/láblécek páratlan és páros oldalakhoz.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

Beállítjuk az oldal paramétereit, beleértve a fejléc távolságát, majd áttérünk a fő fejlécre (`HeaderPrimary`). Szöveg hozzáadására és a fejléc formázására a dokumentumgenerátort használjuk.

## 4. lépés: Szúrjon be egy képet és szöveget a fő fejlécbe

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

A dokumentumgenerátorral beszúrunk egy képet a fő fejléc bal felső sarkába, majd jobbra igazított szöveget adunk hozzá.

## 5. lépés: Szúrjon be egy táblázatot a fő láblécbe

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();
```

## 6. lépés: Új oldal hozzáadása és fejlécek/láblécek beállítása

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Ennek a szakasznak nincs szüksége más fejlécre/láblécre az első oldalhoz, csak egy címlapra van szükségünk a dokumentumban,
//és ennek az oldalnak a fejléce/lábléce már meghatározásra került az előző részben.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Ez a szakasz alapértelmezés szerint az előző szakasz fejléceit/lábléceit jeleníti meg. A hivatkozás megszakításához hívja a currentSection.HeadersFooters.LinkToPrevious(false),
// az új szakasz oldalszélessége eltérő, ezért különböző cellaszélességeket kell beállítanunk egy lábléctáblázathoz.
currentSection.HeadersFooters.LinkToPrevious(false);

// Ha a már meglévő fejléceket/lábléceket szeretnénk használni ehhez a szakaszhoz,
//de néhány apró változtatással érdemes lehet a fejléceket/lábléceket másolni
// az előző részből, és alkalmazzuk a szükséges változtatásokat ott, ahol szeretnénk.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Mentse el a dokumentumot
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Oldaltörést és szakasztörést adunk, hogy létrehozzunk egy új oldalt, ahol az elsődleges fejlécek/láblécek láthatók lesznek. Beállítjuk az új szakasz paramétereit, majd a`CopyHeadersFootersFromPreviousSection` módszer a fejlécek/láblécek előző szakaszból való másolásához. Végül beállítjuk a megfelelő cellaszélességeket a fő lábléctáblázathoz, és elmentjük a dokumentumot.

### Példa forráskódra fejlécek és láblécek létrehozásához az Aspose.Words for .NET segítségével

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// Adja meg, hogy az első oldal fejlécei/láblécei eltérjenek-e a többi oldaltól.
// A PageSetup.OddAndEvenPagesHeaderFooter tulajdonságot is megadhatja
// különböző fejlécek/láblécek páratlan és páros oldalakhoz.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

pageSetup.HeaderDistance = 20;
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Helyezzen be egy elhelyezett képet a fejléc felső/bal sarkába.
// Az oldal felső/bal szélétől mért távolság 10 pont.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Két cellás táblázatot használunk, hogy a szöveg egy részét a sorban készítsük el (oldalszámozással).
// Balra igazítandó, a szöveg másik része (szerzői joggal) pedig jobbra igazítandó.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// PAGE és NUMPAGES mezőket használ az aktuális oldalszám és sok oldal automatikus kiszámításához.
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();

// Oldaltöréssel hozzon létre egy második oldalt, amelyen az elsődleges fejléc/lábléc látható.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Ennek a szakasznak nincs szüksége más első oldali fejlécre/láblécre, csak egy címlapra van szükség a dokumentumban,
//és ennek az oldalnak a fejléce/lábléce már meghatározásra került az előző részben.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Ez a szakasz az előző szakasz fejléceit/lábléceit jeleníti meg
// alapértelmezés szerint hívja a currentSection.HeadersFooters.LinkToPrevious(false) elemet az oldalszélesség törléséhez
// eltérő az új szakaszban, ezért különböző cellaszélességeket kell beállítanunk egy lábléctáblázathoz.
currentSection.HeadersFooters.LinkToPrevious(false);

// Ha ehhez a szakaszhoz a már meglévő fejléc/lábléc készletet szeretnénk használni.
// Kisebb módosításokkal azonban célszerű lehet a fejléceket/lábléceket másolni
// az előző részből, és alkalmazzuk a szükséges módosításokat ott, ahol szeretnénk.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### GYIK

#### K: Hogyan adhatok fejlécet a dokumentumomhoz az Aspose.Wordsben?

 V: Ha fejlécet szeretne hozzáadni a dokumentumhoz az Aspose.Words alkalmazásban, használja a`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` módszer. Ez a módszer elsődleges címsort ad a dokumentum első szakaszához.

#### K: Hogyan adhatok láblécet a dokumentumomhoz az Aspose.Words alkalmazásban?

 V: Ha láblécet szeretne hozzáadni a dokumentumhoz az Aspose.Words alkalmazásban, használja a`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`módszer. Ez a módszer elsődleges láblécet ad a dokumentum első szakaszához.

#### K: Hogyan adhatok hozzá szöveget az Aspose.Words fejlécéhez vagy láblécéhez?

 V: Ha szöveget szeretne hozzáadni az Aspose.Words fejlécéhez vagy láblécéhez, használja a`HeaderFooter.Paragraphs` tulajdonságot a fejléc vagy lábléc bekezdésgyűjteményének lekéréséhez, majd adjon hozzá egy, a szövegét tartalmazó bekezdést ehhez a gyűjteményhez a segítségével`ParagraphCollection.Add` módszer.

#### K: Testreszabhatom a fejléc vagy lábléc tartalmát képekkel és oldalszámokkal az Aspose.Wordsben?

 V: Igen, személyre szabhatja a fejléc- vagy lábléc tartalmát képekkel és oldalszámokkal az Aspose.Words-ben. Használhat olyan objektumokat, mint pl`Shape` képek és objektumok hozzáadásához`Field` oldalszámok hozzáadásához a fejléchez vagy a lábléchez.

#### K: Módosíthatom az Aspose.Words fejlécében vagy láblécében lévő szöveg betűtípusát, méretét és színét?

 V: Igen, módosíthatja az Aspose.Words fejlécében vagy láblécében lévő szöveg betűtípusát, méretét és színét. Hozzáférhet a szövegformázási tulajdonságokhoz, mint pl`Font` a betűtípus megváltoztatásához,`Size` a méret beállításához, és`Color` szöveg színének beállításához.