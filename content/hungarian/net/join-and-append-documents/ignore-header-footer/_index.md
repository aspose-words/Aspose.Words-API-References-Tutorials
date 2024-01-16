---
title: A fejléc láblécének figyelmen kívül hagyása
linktitle: A fejléc láblécének figyelmen kívül hagyása
second_title: Aspose.Words Document Processing API
description: Az Aspose.Words for .NET használatával megtudhatja, hogyan fűzhet hozzá egy dokumentumot a fejléc- és lábléctartalom figyelmen kívül hagyásával.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/ignore-header-footer/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET egy dokumentum hozzáfűzésére, miközben figyelmen kívül hagyja a fejléc és a lábléc tartalmát. A mellékelt forráskód bemutatja, hogyan kell beállítani az importálási formátumbeállításokat a fejléc és a lábléc kizárására a hozzáfűzési folyamat során.

## 1. lépés: Állítsa be a projektet

Győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

-  Aspose.Words for .NET könyvtár telepítve. Letöltheti innen[Aspose.Releases]https://releases.aspose.com/words/net/ vagy használja a NuGet csomagkezelőt a telepítéséhez.
- Egy dokumentumkönyvtár elérési útja, ahol a forrás- és céldokumentum található.

## 2. lépés: Nyissa meg a forrás- és céldokumentumot

 Nyissa meg a forrás- és céldokumentumot a segítségével`Document` osztályú konstruktőr. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## 3. lépés: Állítsa be az importálási formátum beállításait

 Hozzon létre egy példányt a`ImportFormatOptions` osztályt, és állítsa be a`IgnoreHeaderFooter`tulajdonát`false`. Ez biztosítja, hogy a fejléc és a lábléc tartalom szerepeljen a hozzáfűzési folyamat során.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## 4. lépés: A forrásdokumentum hozzáfűzése a céldokumentumhoz

 Használja a`AppendDocument` a céldokumentum módszere a forrásdokumentum hozzáfűzéséhez. Pass`ImportFormatMode.KeepSourceFormatting` második paraméterként, harmadikként pedig az import formátum beállításai.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## 5. lépés: Mentse el a céldokumentumot

 Végül mentse el a módosított céldokumentumot a`Save` módszere a`Document` tárgy.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Ezzel befejeződik a dokumentum hozzáfűzésének megvalósítása, miközben figyelmen kívül hagyja a fejléc és a lábléc tartalmát az Aspose.Words for .NET használatával.

### Példa forráskód a fejléc láblécének figyelmen kívül hagyásához az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```