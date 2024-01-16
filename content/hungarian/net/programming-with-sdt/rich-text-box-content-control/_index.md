---
title: Rich Text Box Content Control
linktitle: Rich Text Box Content Control
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre rich text box tartalomvezérlőt Word-dokumentumban az Aspose.Words for .NET segítségével, amely lehetővé teszi a szöveg formázását és stílusát.
type: docs
weight: 10
url: /hu/net/programming-with-sdt/rich-text-box-content-control/
---

Ez az oktatóanyag bemutatja, hogyan hozhat létre rich text box tartalomvezérlőt Word-dokumentumban az Aspose.Words for .NET használatával. A gazdag szövegmezők tartalomvezérlői lehetővé teszik a felhasználók számára, hogy különféle stílusokkal és formázási beállításokkal írják be és formázzák a szöveget.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak a tényleges elérési útjával, ahová a dokumentumot menteni szeretné.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre egy dokumentumot és egy StructuredDocumentTag-et
 Hozzon létre egy új példányt a`Document` osztály és a`StructuredDocumentTag` a rich text box tartalomvezérlőjének megjelenítésére. Adja meg`SdtType.RichText` mint a típus és`MarkupLevel.Block` jelölési szintként blokkszintű rich text box létrehozásához.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## 3. lépés: Hozzon létre és formázza meg a Rich Text tartalmat
Hozzon létre egy bekezdést, és futtassa a formázott szöveges tartalom megjelenítéséhez. Állítsa be a szöveget és a formázási beállításokat, például színt, betűtípust stb.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## 4. lépés: Adja hozzá a Rich Text tartalmat a Tartalomvezérlőhöz
Adja hozzá a formázott szöveget tartalmazó bekezdést a`ChildNodes` a rich text box tartalomvezérlőjének gyűjteménye.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## 5. lépés: Adja hozzá a tartalomvezérlőt a dokumentumhoz
 A formázott szövegmező tartalomvezérlőjét hozzáfűzi a dokumentum törzséhez a gombbal`AppendChild` a dokumentum első szakaszának törzsének módszere.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## 6. lépés: Mentse el a dokumentumot
 Mentse a dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithSdt.RichTextBoxContentControl.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Példa forráskód a Rich Text Box Content Controlhoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

Ez az! Sikeresen létrehozott egy rich text box tartalomvezérlőt a Word-dokumentumban az Aspose.Words for .NET használatával.