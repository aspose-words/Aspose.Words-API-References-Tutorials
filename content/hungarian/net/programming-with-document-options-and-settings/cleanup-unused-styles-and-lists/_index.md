---
title: Tisztítsa meg a nem használt stílusokat és listákat
linktitle: Tisztítsa meg a nem használt stílusokat és listákat
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a nem használt stílusok és listák eltávolításához egy dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, amellyel az Aspose.Words for .NET segítségével megtisztíthatja a nem használt stílusokat és listákat. Ez a funkció lehetővé teszi a dokumentumban nem használt stílusok és listák eltávolítását.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük a Word dokumentumot, amely tartalmazza a nem használt stílusokat és listákat, amelyeket meg akarunk tisztítani. A dokumentum betöltéséhez használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentum található.

## 3. lépés: Tisztítás előtt számolja meg a stílusokat és a listákat

Tisztítás előtt megszámoljuk a dokumentumban szereplő stílusok és listák számát. A számlálók megjelenítéséhez használja a következő kódot:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Ezek az utasítások a tisztítás előtt a dokumentumban található stílusok és listák számát mutatják.

## 4. lépés: Tisztítsa meg a nem használt stílusokat és listákat

Most tisztítsuk meg a nem használt stílusokat és listákat a dokumentumból. Használja a következő kódot a tisztításhoz:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Ez a kód a megadott beállításokkal törli a fel nem használt stílusokat és listákat a dokumentumból. Ebben a példában engedélyeztük a`UnusedStyles` lehetőség a nem használt stílusok eltávolítására és letiltására`UnusedLists` lehetőség a listák megtartására akkor is, ha nem használják őket.

## 5. lépés: Tisztítás után számolja meg a stílusokat és a listákat

A tisztítás elvégzése után újra megszámoljuk a stílusokat és a listákat, hogy ellenőrizzük, nem lettek-e összecsukva. Az új számlálók megjelenítéséhez használja a következő kódot:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Ezek az utasítások a tisztítás után fennmaradó stílusok és listák számát mutatják.

### Példa forráskód a nem használt stílusok és listák tisztításához az Aspose.Words for .NET használatával

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// A beépített stílusokkal kombinálva a dokumentum nyolc stílust tartalmaz.
	// Az egyéni stílusok „használt”-ként vannak megjelölve, amíg a dokumentumban szöveg található
	// ebben a stílusban formázott. Ez azt jelenti, hogy az általunk hozzáadott 4 stílus jelenleg nincs használatban.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//Megtisztítja a fel nem használt stílusokat és listákat a dokumentumból az adott CleanupOptions függvényében.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg a`dataDir` változó.

Most megtanulta, hogyan törölheti ki a nem használt stílusokat és listákat egy dokumentumból az Aspose.Words for .NET segítségével. Az oktatóanyagban található lépésenkénti útmutatót követve könnyedén alkalmazhatja ezt a funkciót saját dokumentumaira.

