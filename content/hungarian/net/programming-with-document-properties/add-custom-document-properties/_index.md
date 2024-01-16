---
title: Egyéni dokumentumtulajdonságok hozzáadása
linktitle: Egyéni dokumentumtulajdonságok hozzáadása
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre útmutató egyéni tulajdonságok hozzáadásához egy dokumentumhoz az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-document-properties/add-custom-document-properties/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, hogy egyéni tulajdonságokat adhasson egy dokumentumhoz az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi egyéni információk hozzáadását a dokumentumhoz.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük azt a Word dokumentumot, amelyhez egyéni tulajdonságokat szeretnénk hozzáadni. A dokumentum betöltéséhez használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentum található.

## 3. lépés: Adjon hozzá egyéni tulajdonságokat

Most adjunk egyéni tulajdonságokat a dokumentumhoz. A tulajdonságok hozzáadásához használja a következő kódot:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Ez a kód először ellenőrzi, hogy az „Authorized” tulajdonság már létezik-e az egyéni tulajdonságokban. Ha létezik, a folyamat megszakad. Ellenkező esetben az egyéni tulajdonságok hozzáadódnak a dokumentumhoz.

### Példa forráskódra az Egyéni dokumentumtulajdonságok hozzáadása az Aspose.Words for .NET használatával funkcióhoz

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg a`dataDir` változó.

Most megtanulta, hogyan adhat egyéni tulajdonságokat egy dokumentumhoz az Aspose.Words for .NET használatával. Az oktatóanyagban található lépésenkénti útmutató követésével könnyedén hozzáadhatja saját egyéni tulajdonságait a dokumentumokhoz.