---
title: Személyes adatok eltávolítása
linktitle: Személyes adatok eltávolítása
second_title: Aspose.Words Document Processing API
description: Útmutató a személyes adatok dokumentumból való eltávolításához lépésről lépésre az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-document-properties/remove-personal-information/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, amellyel személyes adatokat távolíthat el egy dokumentumból az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi az érzékeny személyes adatok, például a szerzőazonosító adatok eltávolítását a dokumentumokból.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben feltöltjük azt a Word dokumentumot, amelyből el szeretnénk távolítani a személyes adatokat. A dokumentum betöltéséhez használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentum található.

## 3. lépés: Törölje a személyes adatokat

 Most engedélyezzük a személyes adatok eltávolítását a`RemovePersonalInformation`tulajdonát`true`. Használja a következő kódot:

```csharp
doc.RemovePersonalInformation = true;
```

Ez a kód aktiválja a személyes adatok törlését a dokumentumban.

## 4. lépés: A dokumentum mentése

Végül elmentjük a dokumentumot a személyes adatok eltávolításával. Használja a következő kódot:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Ez a kód a személyes adatokkal eltávolított dokumentumot egy új fájlba menti.

### Példa forráskódra a Személyes adatok eltávolításához az Aspose.Words segítségével .NET-hez

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg a`dataDir` változó.

Most megtanulta, hogyan távolíthat el személyes adatokat egy dokumentumból az Aspose.Words for .NET segítségével. Az oktatóanyag lépésenkénti útmutatójának követésével könnyedén eltávolíthatja a bizalmas információkat saját dokumentumaiból.