---
title: Csatlakozz a Continuoushoz
linktitle: Csatlakozz a Continuoushoz
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan kapcsolhat össze két dokumentumot folyamatosan a formázás megőrzése mellett az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/join-continuous/
---

Ez az oktatóanyag elmagyarázza, hogyan lehet két dokumentumot folyamatosan összekapcsolni az Aspose.Words for .NET használatával. A mellékelt forráskód bemutatja, hogyan lehet egy dokumentumot hozzáfűzni egy másik dokumentum végéhez, miközben megőrzi az eredeti formázást.

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

## 3. lépés: Állítsa be a folyamatos szakaszindítást

Ha azt szeretné, hogy a forrásdokumentum közvetlenül a céldokumentum tartalma után jelenjen meg, állítsa be a`SectionStart` a forrásdokumentum első szakaszának tulajdonsága`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 4. lépés: Csatolja a forrásdokumentumot

 Csatlakoztassa a forrásdokumentumot a céldokumentumhoz a gombbal`AppendDocument` módszere a`Document` osztály. Állítsa be az importálási formátum módot`ImportFormatMode.KeepSourceFormatting` hogy megőrizze az eredeti stílusokat a forrásdokumentumból.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. lépés: Mentse el a módosított dokumentumot

Végül mentse el a módosított céldokumentumot a`Save` módszere a`Document` tárgy.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

Ezzel befejeződik a két dokumentum Aspose.Words for .NET segítségével történő folyamatos összekapcsolásának megvalósítása.

### Példa a Join Continuous for Aspose.Words for .NET forráskódjához 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// A dokumentum közvetlenül a céldokumentum tartalma után jelenjen meg.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// A forrásdokumentum hozzáfűzése a forrásdokumentumban található eredeti stílusok használatával.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```