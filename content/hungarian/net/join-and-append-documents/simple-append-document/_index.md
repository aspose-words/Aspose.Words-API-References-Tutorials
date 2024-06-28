---
title: Egyszerű dokumentum csatolása
linktitle: Egyszerű dokumentum csatolása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan kapcsolhat össze és fűzhet hozzá megőrzött formázású Word-dokumentumokat az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/simple-append-document/
---

Ez az oktatóanyag végigvezeti az Aspose.Words for .NET Simple Append Document funkciójának használatán. Ez a funkció lehetővé teszi Word-dokumentumok összekapcsolását és hozzáfűzését további lehetőségek nélkül.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

1. Az Aspose.Words for .NET telepítve van. Letöltheti az Aspose webhelyéről, vagy telepítheti a NuGet segítségével.
2. Visual Studio vagy bármely más C# fejlesztői környezet.

## 1. lépés: Inicializálja a dokumentumkönyvtárakat

 Először is be kell állítania a dokumentumkönyvtár elérési útját. Módosítsa az értékét`dataDir` változó ahhoz az elérési úthoz, ahol a dokumentumok találhatók.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a forrás- és céldokumentumot

Ezután be kell töltenie a forrás- és céldokumentumot az Aspose.Words használatával.`Document` osztály. Frissítse a fájlneveket a`Document` konstruktor a dokumentumnevek szerint.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. lépés: Csatolja a forrásdokumentumot a céldokumentumhoz

 Most hozzáfűzheti a forrásdokumentumot a céldokumentumhoz a segítségével`AppendDocument` módszere a`Document` osztály. A`ImportFormatMode.KeepSourceFormatting` paraméter biztosítja, hogy a forrás formázása megmaradjon a hozzáfűzési művelet során.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 4. lépés: Mentse el a záródokumentumot

 Végül mentse el az egyesített dokumentumot az Egyszerű dokumentum csatolás funkcióval a`Save` módszere a`Document` osztály.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Példa forráskódra a Simple Append Documenthez az Aspose.Words for .NET használatával

Íme a teljes forráskód a „Simple Append Document” funkcióhoz C# nyelven az Aspose.Words for .NET használatával:

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Adja hozzá a forrásdokumentumot a céldokumentumhoz extra beállítások nélkül.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

Ez az! Sikeresen megvalósította a Dokumentum egyszerű hozzáfűzése funkciót az Aspose.Words for .NET használatával. A végleges dokumentum az egyesített tartalmat fogja tartalmazni, a forrásformázás megőrizve.