---
title: Linkfejlécek láblécek
linktitle: Linkfejlécek láblécek
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan kapcsolhat össze fejlécet és láblécet Word-dokumentumok egyesítése és hozzáfűzése közben az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/link-headers-footers/
---

Ez az oktatóanyag végigvezeti az Aspose.Words for .NET Linkfejlécek lábléc funkciójának használatán. Ez a funkció lehetővé teszi több Word-dokumentum összekapcsolását és hozzáfűzését, miközben a forrásdokumentum fejléceit és lábléceit összekapcsolja a céldokumentum előző szakaszával.

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

## 3. lépés: Állítsa be a csatolt dokumentumot, hogy új oldalon jelenjen meg

 Annak biztosításához, hogy a forrásdokumentum tartalma a céldokumentum új oldalán jelenjen meg, be kell állítania a`SectionStart` a forrásdokumentum első szakaszának tulajdonsága`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## 4. lépés: Kapcsolja össze a fejléceket és lábléceket az előző részhez

 A forrásdokumentum fejléceinek és lábléceinek a céldokumentum előző részéhez való kapcsolásához használhatja a`LinkToPrevious` módszere a`HeadersFooters` Gyűjtemény. Áthaladással`true` paraméterként felülírja a forrásdokumentum meglévő fejléceit vagy lábléceit.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## 5. lépés: Csatolja a forrásdokumentumot a céldokumentumhoz

 Most hozzáfűzheti a forrásdokumentumot a céldokumentumhoz a segítségével`AppendDocument` módszere a`Document` osztály. A`ImportFormatMode.KeepSourceFormatting` paraméter biztosítja, hogy a forrás formázása megmaradjon a hozzáfűzési művelet során.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6. lépés: Mentse el a záródokumentumot

 Végül mentse el az egyesített dokumentumot a csatolt fejlécekkel és láblécekkel a`Save` módszere a`Document` osztály.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Példa forráskód link fejlécek láblécéhez az Aspose.Words for .NET használatával 

Íme a teljes forráskód a "Link Headers Footers" funkcióhoz C# nyelven az Aspose.Words for .NET használatával:


```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Állítsa be a csatolt dokumentumot úgy, hogy új oldalon jelenjen meg.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Kapcsolja össze a forrásdokumentum fejléceit és lábléceit az előző részhez.
	// Ez felülír minden fejlécet vagy láblécet, amely már megtalálható a forrásdokumentumban.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

Ez az! Sikeresen implementálta a Link Headers Footers funkciót az Aspose.Words for .NET használatával. A végső dokumentum az összevont tartalmat tartalmazza majd a forrásdokumentum fejléceivel és lábléceivel, amelyek a céldokumentum előző szakaszára hivatkoznak.