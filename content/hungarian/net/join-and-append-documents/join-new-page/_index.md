---
title: Csatlakozz az új oldalhoz
linktitle: Csatlakozz az új oldalhoz
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan kapcsolhat össze két dokumentumot egy új oldalon, miközben megőrzi a formázást az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/join-new-page/
---

Ez az oktatóanyag elmagyarázza, hogyan kapcsolhat össze két dokumentumot egy új oldalon az Aspose.Words for .NET használatával. A megadott forráskód bemutatja, hogyan lehet egy dokumentumot hozzáfűzni egy másik dokumentum végéhez, miközben a hozzáfűzött dokumentumot új oldalon kezdi.

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

## 3. lépés: Új oldalszakasz beállítása

 A csatolt dokumentum új oldalon való indításához állítsa be a`SectionStart` a forrásdokumentum első szakaszának tulajdonsága`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## 4. lépés: Csatolja a forrásdokumentumot

 Csatlakoztassa a forrásdokumentumot a céldokumentumhoz a gombbal`AppendDocument` módszere a`Document` osztály. Állítsa be az importálási formátum módot`ImportFormatMode.KeepSourceFormatting` hogy megőrizze az eredeti stílusokat a forrásdokumentumból.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. lépés: Mentse el a módosított dokumentumot

Végül mentse el a módosított céldokumentumot a`Save` módszere a`Document` tárgy.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

Ezzel befejeződik a két dokumentum egy új oldalon történő egyesítése az Aspose.Words for .NET használatával.

### Példa forráskódra a Csatlakozás új oldalhoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Állítsa be a csatolt dokumentumot úgy, hogy egy új oldalon induljon.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// A forrásdokumentum hozzáfűzése a forrásdokumentumban található eredeti stílusok használatával.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```