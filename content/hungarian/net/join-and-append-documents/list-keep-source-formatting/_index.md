---
title: Listázza a Forrás formázásának megtartását
linktitle: Listázza a Forrás formázásának megtartását
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan őrizheti meg a lista formázását Word-dokumentumok Aspose.Words for .NET segítségével történő egyesítése és hozzáfűzése közben.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/list-keep-source-formatting/
---

Ez az oktatóanyag végigvezeti az Aspose.Words for .NET List Keep Source Formatting szolgáltatásának használatán. Ez a funkció lehetővé teszi a Word-dokumentumok összekapcsolását és hozzáfűzését, miközben megőrzi a listák forrásformázását.

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 3. lépés: Állítsa a forrásdokumentumot Folyamatos áramlásra

 Annak érdekében, hogy a forrásdokumentumból származó tartalom folyamatosan folyjon a céldokumentumhoz fűzve, be kell állítania a`SectionStart` a forrásdokumentum első szakaszának tulajdonsága`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 4. lépés: Csatolja a forrásdokumentumot a céldokumentumhoz

 Most hozzáfűzheti a forrásdokumentumot a céldokumentumhoz a segítségével`AppendDocument` módszere a`Document` osztály. A`ImportFormatMode.KeepSourceFormatting`paraméter biztosítja, hogy a forrás formázása, beleértve a listák formázását is, megmaradjon az append művelet során.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. lépés: Mentse el a záródokumentumot

 Végül mentse el az egyesített dokumentumot a Lista Forrásformázás megőrzése funkcióval a`Save` módszere a`Document` osztály.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Példa forráskódra a List Keep Source formázáshoz az Aspose.Words for .NET használatával 

Íme a List Keep Source Formatting szolgáltatás teljes forráskódja C# nyelven az Aspose.Words for .NET használatával:

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Add hozzá a dokumentum tartalmát, hogy az folyamatosan folyjon.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

Ez az! Sikeresen implementálta a List Keep Source Formatting szolgáltatást az Aspose.Words for .NET használatával. A végső dokumentum az összevont tartalmat fogja tartalmazni, a forrásdokumentum listaformátumának megőrzésével.