---
title: Dokumentumoldal beállítása
linktitle: Dokumentumoldal beállítása
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a dokumentumelrendezés beállításához az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-document-options-and-settings/document-page-setup/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon a dokumentumelrendezés konfigurálásához az Aspose.Words for .NET segítségével. Ezzel a funkcióval beállíthatja az elrendezési módot, a soronkénti karakterek számát és az oldalankénti sorok számát.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük a konfigurálni kívánt Word dokumentumot. A dokumentum betöltéséhez használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentum található.

## 3. lépés: Az elrendezés beállítása

Most állítsuk be a dokumentum elrendezését. A következő kóddal állíthatja be az elrendezési módot, a soronkénti karakterek számát és az oldalankénti sorok számát:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Ez a kód „Rács”-ra állítja az elrendezési módot, majd megadja a soronkénti karakterek számát és az oldalankénti sorok számát.

### Példa forráskódra a dokumentumoldal-beállításhoz az Aspose.Words for .NET használatával


```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Állítsa be egy szakasz elrendezési módját, amely lehetővé teszi a dokumentumrács viselkedésének meghatározását.
	// Vegye figyelembe, hogy a Dokumentumrács fül láthatóvá válik az MS Word Oldalbeállítás párbeszédpaneljén.
	// ha valamelyik ázsiai nyelvet szerkesztőnyelvként határozzuk meg.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg a`dataDir` változó.

Most megtanulta, hogyan konfigurálhatja egy dokumentum elrendezését az Aspose.Words for .NET használatával. Az oktatóanyag lépésenkénti útmutatójának követésével könnyedén testreszabhatja saját dokumentumai elrendezését.