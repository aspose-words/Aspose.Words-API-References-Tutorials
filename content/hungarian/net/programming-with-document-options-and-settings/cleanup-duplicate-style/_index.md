---
title: Ismétlődő stílus tisztítása
linktitle: Ismétlődő stílus tisztítása
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre útmutató az ismétlődő stílusok eltávolításához egy dokumentumban az Aspose.Words for .NET használatával. Teljes forráskód tartalmazza.
type: docs
weight: 10
url: /hu/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük a C# forráskódon az Aspose.Words for .NET segítségével az ismétlődő stílusok eltávolításához. Ez a funkció segít eltávolítani az ismétlődő stílusokat a dokumentumból.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük a Word dokumentumot, amelyet meg akarunk tisztítani. A dokumentum betöltéséhez használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentum található.

## 3. lépés: Tisztítás előtt számolja meg a stílusokat

Mielőtt folytatná a tisztítást, megszámoljuk a dokumentumban szereplő stílusok számát. Használja a következő kódot a stílusok számának megjelenítéséhez:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Ez az utasítás a dokumentumban található stílusok számát jeleníti meg.

## 4. lépés: Tisztítsa meg az ismétlődő stílusokat

Most tisztítsuk meg az ismétlődő stílusokat a dokumentumból. Használja a következő kódot a tisztításhoz:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Ez a kód a megadott beállítások segítségével eltávolítja az ismétlődő stílusokat a dokumentumból. Ebben a példában engedélyeztük a`DuplicateStyle` lehetőség az ismétlődő stílusok törlésére.

## 5. lépés: Tisztítás után számolja meg a stílusokat

tisztítás elvégzése után újra megszámoljuk a stílusok számát, hogy ellenőrizzük, nem csökkent-e. Használja a következő kódot az új stílusok számának megjelenítéséhez:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Ez az utasítás a tisztítás után fennmaradó stílusok számát jeleníti meg.

### Példa a Cleanup Duplicate Style forráskódjához az Aspose.Words for .NET használatával

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// A stílusok száma a tisztítás előtt.
	Console.WriteLine(doc.Styles.Count);

	// Megtisztítja az ismétlődő stílusokat a dokumentumból.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	// A stílusok száma a tisztítás után csökkent.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```