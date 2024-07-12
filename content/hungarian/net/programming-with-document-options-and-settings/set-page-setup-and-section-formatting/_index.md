---
title: Állítsa be az oldalbeállítást és a szakaszformázást
linktitle: Állítsa be az oldalbeállítást és a szakaszformázást
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a dokumentum elrendezésének és szakaszformázásának beállításához az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, hogy beállíthassa az elrendezést és a szakasz formázását az Aspose.Words for .NET segítségével. Ezzel a funkcióval beállíthatja az oldal tájolását, a margókat és a papírméretet.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum létrehozása

Ebben a lépésben új dokumentumot hozunk létre. A dokumentum létrehozásához és a konstruktor inicializálásához használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` annak a könyvtárnak az elérési útjával, ahová a dokumentumot menteni szeretné.

## 3. lépés: Az elrendezés beállítása és a dokumentum mentése

Most állítsuk be a dokumentum elrendezését. Használja a következő kódot a tájolás, a margók és a papírméret beállításához:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Ez a kód az oldal tájolását fekvőre állítja, a bal margót 50-re, a papírméretet pedig 10x14-re.

### Példa forráskód az oldalbeállítás és szakaszformázás beállításához az Aspose.Words for .NET használatával

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

 Ügyeljen arra, hogy megadja annak a könyvtárnak a megfelelő elérési útját, ahová a dokumentumot menteni szeretné`dataDir` változó.

Most megtanulta, hogyan konfigurálhatja a dokumentumok elrendezését és szakaszformázását az Aspose.Words for .NET használatával. Az oktatóanyagban található lépésenkénti útmutató követésével könnyedén testreszabhatja saját dokumentumai elrendezését és formázását.