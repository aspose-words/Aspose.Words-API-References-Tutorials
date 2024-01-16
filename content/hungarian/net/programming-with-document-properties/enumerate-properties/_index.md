---
title: Tulajdonságok felsorolása
linktitle: Tulajdonságok felsorolása
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a dokumentum tulajdonságainak számbavételéhez az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-document-properties/enumerate-properties/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, hogy felsorolhassa a dokumentum tulajdonságait az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi a dokumentum beépített és egyéni tulajdonságainak elérését.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük azt a Word dokumentumot, amelynek tulajdonságait listázni szeretnénk. A dokumentum betöltéséhez használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentum található.

## 3. lépés: Tulajdonságok felsorolása

Most soroljuk fel a dokumentum tulajdonságait, mind a beépített, mind az egyéni tulajdonságokat. Használja a következő kódot:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Ez a kód megjeleníti a dokumentum nevét, majd felsorolja a beépített és egyéni tulajdonságokat, megjelenítve azok nevét és értékét.

### Példa forráskód az Enumerate Properties programhoz az Aspose.Words for .NET használatával

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg a`dataDir` változó.

Most megtanulta, hogyan sorolhatja fel a dokumentum tulajdonságait az Aspose.Words for .NET használatával. Az ebben az oktatóanyagban található, lépésenkénti útmutatót követve könnyedén elérheti és megtekintheti saját dokumentumai tulajdonságait.

