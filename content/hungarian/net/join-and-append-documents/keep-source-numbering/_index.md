---
title: Tartsa meg a forrásszámozást
linktitle: Tartsa meg a forrásszámozást
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan fűzhet hozzá egy dokumentumot, miközben megőrzi a forrásszámozás formázását az Aspose.Words for .NET-ben.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/keep-source-numbering/
---

Ez az oktatóanyag elmagyarázza, hogyan lehet forrásdokumentumot hozzáfűzni a céldokumentumhoz, miközben megőrzi a számozott bekezdések eredeti számozási formázását az Aspose.Words for .NET használatával.

## 1. lépés: Állítsa be a projektet

Győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

-  Aspose.Words for .NET könyvtár telepítve. Letöltheti innen[Aspose.Releases]https://releases.aspose.com/words/net/ vagy használja a NuGet csomagkezelőt a telepítéséhez.
- Egy dokumentumkönyvtár elérési útja, ahová a forrás és a cél dokumentumok mentésre kerülnek.

## 2. lépés: Hozza létre a cél- és forrásdokumentumot

 Példányok létrehozása a`Document` a cél- és forrásdokumentumokhoz.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. lépés: Tartsa meg a forrás számozását importáláskor

 Ha meg szeretné őrizni a számozott bekezdések számozási formázását a forrásdokumentumból, hozzon létre egy példányt`ImportFormatOptions` és állítsa be`KeepSourceNumbering` nak nek`true` . Használj`NodeImporter` csomópontok importálásához a forrásdokumentumból a céldokumentumba, megadva`ImportFormatMode.KeepSourceFormatting` és a`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## 4. lépés: Importáljon és fűzzen hozzá bekezdéseket

 Ismételje meg a forrásdokumentum bekezdéseit, és importálja az egyes bekezdéseket a céldokumentumba a segítségével`importer`. Az importált csomópontok hozzáfűzése a céldokumentum törzséhez.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## 5. lépés: Mentse el a módosított dokumentumot

 Mentse el a módosított dokumentumot a`Save` módszere a`Document` tárgy.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Ezzel befejeződik a forrásdokumentumnak a céldokumentumhoz való hozzáfűzése, miközben megtartja az eredeti számozási formázást az Aspose.Words for .NET használatával.

### Példa forráskód a Keep Source Numbering használatához az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Tartsa meg a forráslista formázását számozott bekezdések importálásakor.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```