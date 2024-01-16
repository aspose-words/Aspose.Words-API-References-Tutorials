---
title: Távolítsa el az egyéni dokumentum tulajdonságait
linktitle: Távolítsa el az egyéni dokumentum tulajdonságait
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre egyéni tulajdonságok eltávolításához egy dokumentumból az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-document-properties/remove-custom-document-properties/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, amellyel egyéni tulajdonságokat távolíthat el egy dokumentumból az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi egy adott egyéni tulajdonság eltávolítását a dokumentumból.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük azt a Word dokumentumot, amelyből az egyéni tulajdonságokat el akarjuk távolítani. A dokumentum betöltéséhez használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentum található.

## 3. lépés: Egyéni tulajdonságok törlése

Most távolítsunk el egy adott egyéni tulajdonságot a dokumentumból. Használja a következő kódot:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Ez a kód eltávolítja az "Engedélyezett dátum" egyéni tulajdonságot a dokumentumból. Az "Engedélyezés dátuma" lecserélheti az eltávolítani kívánt egyéni tulajdonság nevére.

### Példa forráskód az Egyéni dokumentumtulajdonságok eltávolításához az Aspose.Words for .NET használatával

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg a`dataDir` változó.

Most megtanulta, hogyan távolíthat el egyéni tulajdonságokat egy dokumentumból az Aspose.Words for .NET használatával. Az oktatóanyagban található lépésenkénti útmutató követésével könnyedén eltávolíthatja az egyéni tulajdonságokat saját dokumentumaiból.