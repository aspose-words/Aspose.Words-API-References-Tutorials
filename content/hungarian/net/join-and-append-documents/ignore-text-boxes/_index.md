---
title: Szövegdobozok figyelmen kívül hagyása
linktitle: Szövegdobozok figyelmen kívül hagyása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan fűzhet hozzá egy dokumentumot, miközben figyelmen kívül hagyja a szövegdoboz formázását az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/ignore-text-boxes/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET egy dokumentum hozzáfűzésére, miközben megőrzi a szövegdobozok formázását. A mellékelt forráskód bemutatja, hogyan kell beállítani az importálási formátumbeállításokat, hogy a hozzáfűzési folyamat során szövegdobozokat is tartalmazzon.

## 1. lépés: Állítsa be a projektet

Győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

-  Aspose.Words for .NET könyvtár telepítve. Letöltheti innen[Aspose.Releases]https://releases.aspose.com/words/net/ vagy használja a NuGet csomagkezelőt a telepítéséhez.
- Egy dokumentumkönyvtár elérési útja, ahol a forrás- és céldokumentum található.

## 2. lépés: Nyissa meg a forrás- és céldokumentumot

 Nyissa meg a forrás- és céldokumentumot a segítségével`Document` osztályú konstruktőr. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. lépés: Állítsa be az importálási formátum beállításait

 Hozzon létre egy példányt a`ImportFormatOptions` osztályt, és állítsa be a`IgnoreTextBoxes`tulajdonát`false`. Ez biztosítja, hogy a szövegdobozok belekerüljenek a hozzáfűzési folyamat során, miközben megőrzik formázásukat.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## 4. lépés: Szövegdoboz tartalmának hozzáfűzése

 Hozzon létre egy`NodeImporter`objektumot, és ezzel importálhatja a szövegdoboz-csomópontokat a forrásdokumentumból a céldokumentumba. Ismételje meg a forrásdokumentum minden bekezdését, és importálja azokat a céldokumentumba.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## 5. lépés: Mentse el a céldokumentumot

Végül mentse el a módosított céldokumentumot a`Save` módszere a`Document` tárgy.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

Ezzel befejeződik a dokumentum hozzáfűzésének megvalósítása, miközben megőrzi a szövegdoboz formázását az Aspose.Words for .NET használatával.

### Példa forráskódra a szövegdobozok figyelmen kívül hagyásához az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Importáláskor tartsa meg a forrás szövegdobozok formázását.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```