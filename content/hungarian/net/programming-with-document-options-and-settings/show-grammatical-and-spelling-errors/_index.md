---
title: Nyelvtani és helyesírási hibák megjelenítése
linktitle: Nyelvtani és helyesírási hibák megjelenítése
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a nyelvtani és helyesírási hibák megjelenítésének lehetővé tételéhez egy dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, hogy lehetővé tegye a nyelvtani és helyesírási hibák megjelenítését az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi a nyelvtani és helyesírási hibák megtekintését a dokumentumban.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük azt a Word dokumentumot, amelyhez a nyelvtani és helyesírási hibákat szeretnénk megjeleníteni. A dokumentum betöltéséhez használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentum található.

## 3. lépés: Engedélyezze a hibakijelzést

Most engedélyezzük a nyelvtani és helyesírási hibák megjelenítését a dokumentumban. A hibakijelzés engedélyezéséhez használja a következő kódot:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Ez a kód lehetővé teszi a nyelvtani hibák megjelenítését (`ShowGrammaticalErrors`) és helyesírási hibák (`ShowSpellingErrors`) a dokumentumban.

### Példa forráskód a Nyelvtani és helyesírási hibák megjelenítéséhez az Aspose.Words for .NET használatával

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg a`dataDir` változó.

Most megtanulta, hogyan engedélyezheti a nyelvtani és helyesírási hibák megjelenítését egy dokumentumban az Aspose.Words for .NET segítségével. Az oktatóanyagban található lépésenkénti útmutató követésével könnyedén engedélyezheti ezt a funkciót saját dokumentumaiban.