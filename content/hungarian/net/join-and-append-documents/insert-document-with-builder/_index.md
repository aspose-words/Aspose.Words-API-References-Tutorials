---
title: Dokumentum beszúrása a Builder segítségével
linktitle: Dokumentum beszúrása a Builder segítségével
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be egy dokumentumot egy másik dokumentum végére az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/insert-document-with-builder/
---

 Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET egy dokumentum másik dokumentumba történő beillesztéséhez a`DocumentBuilder` osztály. A mellékelt forráskód bemutatja, hogyan lehet egy dokumentumot beszúrni egy másik dokumentum végére, miközben megőrzi a forrás formázását.

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

## 3. lépés: Inicializálja a DocumentBuildert

 Hozzon létre egy új példányt a`DocumentBuilder` osztályt, és paraméterként adja át a céldokumentumot.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## 4. lépés: Helyezze el a DocumentBuildert

Mozdítsd meg a`DocumentBuilder` a dokumentum végére a gombbal`MoveToDocumentEnd` módszer. Oldaltörés beszúrásával elválaszthatja a meglévő tartalmat a beillesztett dokumentumtól.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## 5. lépés: Helyezze be a forrásdokumentumot

 Használja a`InsertDocument` módszere a`DocumentBuilder` osztályt a forrásdokumentum beszúrásához a céldokumentumba. Állítsa be az importálási formátum módot`ImportFormatMode.KeepSourceFormatting` hogy megőrizze a forrás formázását.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6. lépés: Mentse el a módosított dokumentumot

Végül mentse el a módosított céldokumentumot a`Save` módszere a`Document` tárgy.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Ezzel befejeződik egy dokumentum másik dokumentumba történő beszúrása az Aspose.Words for .NET használatával.

### Példa forráskód az Insert Document With Builder alkalmazáshoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```