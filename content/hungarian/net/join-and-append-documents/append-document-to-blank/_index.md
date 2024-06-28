---
title: Dokumentum hozzáfűzése az üreshez
linktitle: Dokumentum hozzáfűzése az üreshez
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan lehet dokumentumot hozzáfűzni egy üres céldokumentumhoz az Aspose.Words for .NET alkalmazásban.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/append-document-to-blank/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET egy dokumentum tartalmának hozzáfűzéséhez egy üres céldokumentumhoz. A mellékelt forráskód bemutatja, hogyan lehet új dokumentumot létrehozni, eltávolítani a tartalmát, majd hozzáfűzni a forrásdokumentumot.

## 1. lépés: Állítsa be a projektet

Győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

-  Aspose.Words for .NET könyvtár telepítve. Letöltheti innen[Aspose.Releases]https://releases.aspose.com/words/net/ vagy használja a NuGet csomagkezelőt a telepítéséhez.
- Egy dokumentumkönyvtár elérési útja, ahol a forrás- és céldokumentum található.

## 2. lépés: Hozzon létre egy új céldokumentumot

 Újat csinálni`Document` objektum a céldokumentumhoz.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## 3. lépés: Távolítsa el a meglévő tartalmat a céldokumentumból

 A céldokumentum tisztaságának biztosítása érdekében távolítsa el a dokumentumból az összes meglévő tartalmat a`RemoveAllChildren` módszer.

```csharp
dstDoc.RemoveAllChildren();
```

## 4. lépés: A forrásdokumentum hozzáfűzése a céldokumentumhoz

 Adja hozzá a forrásdokumentum tartalmát a céldokumentumhoz a segítségével`AppendDocument` módszerrel`ImportFormatMode.KeepSourceFormatting` választási lehetőség.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. lépés: Mentse el a céldokumentumot

Végül mentse el a módosított céldokumentumot a`Save` módszere a`Document` tárgy.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Ezzel befejeződik a dokumentum hozzáfűzése egy üres céldokumentumhoz az Aspose.Words for .NET használatával.

### Példa forráskódra az Append Document To Blank programhoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// A céldokumentum nem üres, ezért gyakran üres oldal jelenik meg a csatolt dokumentum előtt.
	// Ez annak köszönhető, hogy az alapdokumentumnak van egy üres része, és az új dokumentum a következő oldalon kezdődik.
	// A hozzáfűzés előtt távolítsa el az összes tartalmat a céldokumentumból.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```