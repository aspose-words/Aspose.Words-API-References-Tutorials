---
title: Tartsa meg a Forrás formázását
linktitle: Tartsa meg a Forrás formázását
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan fűzhet forrásdokumentumot a céldokumentumhoz, miközben megőrzi az eredeti formázást az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/keep-source-formatting/
---

Ez az oktatóanyag bemutatja, hogyan lehet forrásdokumentumot hozzáfűzni a céldokumentumhoz, miközben megőrzi a forrásdokumentum eredeti formázását az Aspose.Words for .NET használatával.

## 1. lépés: Állítsa be a projektet

Győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

-  Aspose.Words for .NET könyvtár telepítve. Letöltheti innen[Aspose.Releases]https://releases.aspose.com/words/net/ vagy használja a NuGet csomagkezelőt a telepítéséhez.
- Egy dokumentumkönyvtár elérési útja, ahová a forrás és a cél dokumentumok mentésre kerülnek.

## 2. lépés: Hozza létre a cél- és forrásdokumentumot

 Példányok létrehozása a`Document` a cél- és forrásdokumentumokhoz.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## 3. lépés: A forrásdokumentum hozzáfűzése a céldokumentumhoz

 Használja a`AppendDocument` a céldokumentum módszere a forrásdokumentum hozzáfűzéséhez. Pass`ImportFormatMode.KeepSourceFormatting` mint az importálási formátum mód, hogy megőrizze a forrásdokumentum eredeti formázását.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 4. lépés: Mentse el a módosított dokumentumot

 Mentse el a módosított dokumentumot a`Save` módszere a`Document` tárgy.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

Ez befejezi a forrásdokumentumnak a céldokumentumhoz való hozzáfűzését, miközben megtartja az eredeti formázást az Aspose.Words for .NET használatával.

### Példa forráskód a Keep Source Formatting alkalmazáshoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// A forrásdokumentum hozzáfűzése a céldokumentumhoz.
	// Formázási mód átadása a forrásdokumentum eredeti formázásának megőrzéséhez az importálás során.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```