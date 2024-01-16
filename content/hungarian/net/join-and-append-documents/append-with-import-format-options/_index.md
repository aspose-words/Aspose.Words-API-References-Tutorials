---
title: Hozzáfűzi az importálási formátumbeállításokkal
linktitle: Hozzáfűzi az importálási formátumbeállításokkal
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan fűzhet hozzá egy dokumentumot importálási formátumbeállításokkal az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/append-with-import-format-options/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET egyik dokumentum tartalmának a másikhoz importálási formátumbeállításokkal történő hozzáfűzésére. A mellékelt forráskód bemutatja, hogyan kell megnyitni a forrás- és céldokumentumot, megadni az importálási formátumbeállításokat, és hogyan kell hozzáfűzni a forrásdokumentumot a céldokumentumhoz.

## 1. lépés: Állítsa be a projektet

Győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

-  Aspose.Words for .NET könyvtár telepítve. Letöltheti innen[Aspose.Releases]https://releases.aspose.com/words/net/ vagy használja a NuGet csomagkezelőt a telepítéséhez.
- Egy dokumentumkönyvtár elérési útja, ahol a forrás- és céldokumentum található.

## 2. lépés: Nyissa meg a forrás- és céldokumentumot

 Nyissa meg a forrás- és céldokumentumot a segítségével`Document` osztályú konstruktőr. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 3. lépés: Adja meg az importálási formátum beállításait

 Hozzon létre egy példányt a`ImportFormatOptions` osztályba az importálási formátum beállításainak megadásához. Ebben a példában a`KeepSourceNumbering` tulajdonság annak biztosítására, hogy a forrásdokumentumból származó számozás kerüljön felhasználásra, ha ütközés van a céldokumentummal.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## 4. lépés: A forrásdokumentum hozzáfűzése a céldokumentumhoz

 Használja a`AppendDocument` a céldokumentum módszere a forrásdokumentum hozzáfűzéséhez. Pass`ImportFormatMode.UseDestinationStyles` második paraméterként a céldokumentum stílusainak és formázásának használatához.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## 5. lépés: Mentse el a céldokumentumot

 Végül mentse el a módosított céldokumentumot a`Save` módszere a`Document` tárgy.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Ezzel az Aspose.Words for .NET használatával befejeződik egy dokumentum importálási formátumbeállításokkal történő hozzáfűzése.

### Példa forráskódra az Append With Import Format Options programhoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Adja meg, hogy ha a számozás ütközik a forrás- és a céldokumentumban,
	//akkor a forrásdokumentumból származó számozás kerül felhasználásra.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```