---
title: Indítsa újra az oldalszámozást
linktitle: Indítsa újra az oldalszámozást
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan indíthatja újra az oldalszámozást Word-dokumentumok egyesítése és hozzáfűzése közben az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/restart-page-numbering/
---

Ez az oktatóanyag végigvezeti az Aspose.Words .NET oldalszámozás újraindítása funkciójának használatán. Ez a funkció lehetővé teszi Word-dokumentumok összekapcsolását és hozzáfűzését, miközben újraindítja az oldalszámozást a forrásdokumentumban.

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

## 3. lépés: Állítsa be a forrásdokumentumot az oldalszámozás újraindítására

 Az oldalszámozás újraindításához a forrásdokumentumban be kell állítani a`SectionStart` a forrásdokumentum első szakaszának tulajdonsága`SectionStart.NewPage` és állítsa be a`RestartPageNumbering`tulajdonát`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## 4. lépés: Csatolja a forrásdokumentumot a céldokumentumhoz

 Most hozzáfűzheti a forrásdokumentumot a céldokumentumhoz a segítségével`AppendDocument` módszere a`Document` osztály. A`ImportFormatMode.KeepSourceFormatting` paraméter biztosítja, hogy a forrás formázása megmaradjon a hozzáfűzési művelet során.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. lépés: Mentse el a záródokumentumot

 Végül mentse az egyesített dokumentumot úgy, hogy az oldalszámozás újraindítása funkcióval engedélyezve van a`Save` módszere a`Document` osztály.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Példa forráskód az oldalszámozás újraindításához az Aspose.Words használatával .NET-hez

Íme az "Oldalszámozás újraindítása" funkció teljes forráskódja C# nyelven az Aspose.Words for .NET használatával:
 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

Ez az! Sikeresen megvalósította az Oldalszámozás újraindítása funkciót az Aspose.Words for .NET használatával. A végső dokumentum az összevont tartalmat tartalmazza majd a forrásdokumentumban újraindított oldalszámozással.