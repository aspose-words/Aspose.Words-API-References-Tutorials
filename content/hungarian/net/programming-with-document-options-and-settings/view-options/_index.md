---
title: Beállítások megtekintése
linktitle: Beállítások megtekintése
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a dokumentummegjelenítési beállítások konfigurálásához az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-document-options-and-settings/view-options/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon a megjelenítési beállítások konfigurálásához az Aspose.Words for .NET segítségével. Ezzel a funkcióval testreszabhatja a dokumentum nézeti módját és nagyítási szintjét.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük azt a Word dokumentumot, amelynek megjelenítési beállításait szeretnénk konfigurálni. A dokumentum betöltéséhez használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentum található.

## 3. lépés: A megjelenítési beállítások konfigurálása

Most konfiguráljuk a dokumentum megjelenítési beállításait. Használja a következő kódot a megjelenítési mód és a nagyítási szint beállításához:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Ez a kód a nézet módot "PageLayout"-ra, a nagyítási szintet pedig 50%-ra állítja.

### Példa forráskód a Nézetbeállításokhoz az Aspose.Words for .NET használatával

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg a`dataDir` változó.

Most megtanulta, hogyan konfigurálhatja a dokumentummegjelenítési beállításokat az Aspose.Words for .NET használatával. Az oktatóanyagban található lépésenkénti útmutató követésével könnyedén testreszabhatja saját dokumentumai megjelenítését.