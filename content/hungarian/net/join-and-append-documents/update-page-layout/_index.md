---
title: Oldalelrendezés frissítése
linktitle: Oldalelrendezés frissítése
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan frissítheti az oldalelrendezést Word-dokumentumok Aspose.Words for .NET segítségével történő egyesítése és hozzáfűzése során.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/update-page-layout/
---

Ez az oktatóanyag végigvezeti az Aspose.Words for .NET oldalelrendezés frissítése funkciójának használatán. Ez a funkció biztosítja, hogy az oldalelrendezés megfelelően frissüljön a Word-dokumentumok egyesítésekor és hozzáfűzésekor.

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

## 3. lépés: Frissítse a céldokumentum oldalelrendezését

 Annak biztosítására, hogy az oldalelrendezés megfelelően frissüljön a forrásdokumentum hozzáfűzése előtt, meghívhatja a`UpdatePageLayout` módszert a céldokumentumban.

```csharp
dstDoc.UpdatePageLayout();
```

## 4. lépés: Csatolja a forrásdokumentumot a céldokumentumhoz

 Most hozzáfűzheti a forrásdokumentumot a céldokumentumhoz a segítségével`AppendDocument` módszere a`Document` osztály. A`ImportFormatMode.KeepSourceFormatting` paraméter biztosítja, hogy a forrás formázása megmaradjon a hozzáfűzési művelet során.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. lépés: Frissítse újra az oldal elrendezését

 A forrásdokumentum hozzáfűzése után meg kell hívnia a`UpdatePageLayout`metódust ismét a céldokumentumban, hogy biztosítsa, hogy a hozzáfűzés után végrehajtott változtatások megjelenjenek a renderelt kimenetben.

```csharp
dstDoc.UpdatePageLayout();
```

## 6. lépés: Mentse el a záródokumentumot

 Végül mentse az egyesített dokumentumot az Oldalelrendezés frissítése funkcióval a`Save` módszere a`Document` osztály.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Példa forráskód az oldalelrendezés frissítéséhez az Aspose.Words for .NET használatával

Íme a teljes forráskód a C# „Oldalelrendezés frissítése” funkciójához az Aspose.Words for .NET használatával:

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Ha a céldokumentum PDF, kép stb.
	// vagy az UpdatePageLayout a forrásdokumentum előtt kerül meghívásra. Mellékelve van,
	// akkor a későbbi módosítások nem fognak megjelenni a megjelenített kimenetben
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Ahhoz, hogy a változtatások a renderelt kimenetre frissüljenek, az UpdatePageLayoutot újra meg kell hívni.
	// Ha nem hívja meg újra, a hozzáfűzött dokumentum nem jelenik meg a következő renderelés kimenetében.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

Ez az! Sikeresen megvalósította az Oldalelrendezés frissítése funkciót az Aspose.Words for .NET használatával. A végleges dokumentum az egyesített tartalmat tartalmazza majd az oldalelrendezés helyesen frissítve.