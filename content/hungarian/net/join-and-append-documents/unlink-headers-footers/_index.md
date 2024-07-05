---
title: Fejléc-láblécek leválasztása
linktitle: Fejléc-láblécek leválasztása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan kapcsolhat össze és fűzhet hozzá Word-dokumentumokat, miközben leválasztja a fej- és lábléceket az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/unlink-headers-footers/
---

Ez az oktatóanyag végigvezeti az Aspose.Words for .NET fejléc-láblécek leválasztása funkciójának használatán. Ez a funkció lehetővé teszi Word-dokumentumok összekapcsolását és hozzáfűzését, miközben leválasztja a fejléceket és lábléceket a forrásdokumentumról.

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

Ezután be kell töltenie a forrás- és céldokumentumot az Aspose.Words használatával`Document` osztály. Frissítse a fájlneveket a`Document` konstruktor a dokumentumnevek szerint.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. lépés: Szüntesse meg a fejlécek és láblécek összekapcsolását a forrásdokumentumban

 A forrásdokumentum fejléceinek és lábléceinek összekapcsolásának megszüntetéséhez a céldokumentum fejléceinek és lábléceinek folytatásához be kell állítania a`LinkToPrevious` tulajdona a`HeadersFooters` gyűjtemény a forrásdokumentum első részében`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## 4. lépés: Csatolja a forrásdokumentumot a céldokumentumhoz

 Most hozzáfűzheti a forrásdokumentumot a céldokumentumhoz a segítségével`AppendDocument` módszere a`Document` osztály. A`ImportFormatMode.KeepSourceFormatting` paraméter biztosítja, hogy a forrás formázása megmaradjon a hozzáfűzési művelet során.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. lépés: Mentse el a záródokumentumot

 Végül mentse el az egyesített dokumentumot a Fejlécek lábléceinek leválasztása funkcióval a`Save` módszere a`Document` osztály.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Példa forráskód a fejlécek leválasztásához láblécekhez az Aspose.Words for .NET használatával

Íme a teljes forráskód a C#-ban az Aspose.Words for .NET-hez tartozó "Unlink Headers Footers" funkcióhoz:

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Ennek megállításához válassza le a fejléceket és a lábléceket a forrásdokumentumban
	// a céldokumentum fejléceinek és lábléceinek folytatásától.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Ez az! Sikeresen implementálta a Fejlécek lábléceinek szétválasztása funkciót az Aspose.Words for .NET használatával. A végső dokumentum az egyesített tartalmat fogja tartalmazni a céldokumentumtól leválasztott forrásdokumentum fejléceivel és lábléceivel.