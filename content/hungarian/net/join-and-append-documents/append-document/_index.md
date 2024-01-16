---
title: Dokumentum csatolása
linktitle: Dokumentum csatolása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan fűzheti egy dokumentum tartalmát a másikhoz az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/append-document/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET egyik dokumentum tartalmának a másikhoz fűzéséhez. A mellékelt forráskód bemutatja, hogyan lehet megnyitni a forrás- és céldokumentumot, importálni és hozzáfűzni szakaszokat a forrásdokumentumból a céldokumentumhoz.

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

## 3. lépés: A forrásdokumentum szakaszainak hozzáfűzése a céldokumentumhoz

 Keresse át a forrásdokumentum összes szakaszát, és importálja az egyes szakaszokat a céldokumentumba a segítségével`ImportNode` módszer. Ezután fűzze hozzá az importált részt a céldokumentumhoz.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## 4. lépés: Mentse el a céldokumentumot

 Végül mentse el a módosított céldokumentumot a`Save` módszere a`Document` tárgy.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

Ezzel befejeződik a dokumentum Aspose.Words for .NET használatával történő hozzáfűzése.

### Példa forráskódra a Dokumentum hozzáfűzéséhez az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Lapozzon át a forrásdokumentum összes szakaszán.
	// szakasz csomópontjai a Dokumentum csomópont közvetlen gyermekei, így csak felsorolni tudjuk a dokumentumot.
	foreach (Section srcSection in srcDoc)
	{
		// Mivel egy részt másolunk egyik dokumentumból a másikba,
		// szükséges a szakasz csomópont importálása a céldokumentumba.
		// Ez módosítja a dokumentumspecifikus hivatkozásokat a stílusokhoz, listákhoz stb.
		//
		// Egy csomópont importálása létrehozza az eredeti csomópont másolatát, de a másolatot
		// ss készen áll a céldokumentumba való beillesztésre.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Mostantól az új szakaszcsomópont hozzáfűzhető a céldokumentumhoz.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```