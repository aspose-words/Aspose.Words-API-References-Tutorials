---
title: Változók beszerzése
linktitle: Változók beszerzése
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a dokumentumváltozók lekéréséhez az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-document-properties/get-variables/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, amellyel változókat kérhet le egy dokumentumból az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi a dokumentumban meghatározott változók elérését.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük azt a Word dokumentumot, amelyből a változókat szeretnénk lekérni. A dokumentum betöltéséhez használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentum található.

## 3. lépés: Változók lekérése

Most lekérjük a dokumentumban meghatározott változókat. Használja a következő kódot:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

Ez a kód a dokumentumváltozókban lévő minden kulcs-érték páron iterál, és lekéri az egyes változók nevét és értékét. A változókat ezután összefűzi, hogy megjelenítse az egyes változókra vonatkozó információkat.

### Példa forráskód a Get Variables Aspose.Words for .NET használatával forráskódjához

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg a`dataDir` változó.

Most megtanulta, hogyan lehet változókat lekérni egy dokumentumból az Aspose.Words for .NET használatával. Az ebben az oktatóanyagban található lépésenkénti útmutató követésével könnyedén elérheti és megtekintheti saját dokumentumai változóit.