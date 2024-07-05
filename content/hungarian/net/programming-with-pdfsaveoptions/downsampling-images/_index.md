---
title: Csökkentse a PDF-dokumentum méretét a képek mintavételezésével
linktitle: Csökkentse a PDF-dokumentum méretét a képek mintavételezésével
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan csökkentheti a PDF-dokumentum méretét a képek mintavételezésével, amikor az Aspose.Words for .NET segítségével PDF-be konvertál.
type: docs
weight: 10
url: /hu/net/programming-with-pdfsaveoptions/downsampling-images/
---

Ebben az oktatóanyagban végigvezetjük a pdf-dokumentum méretének csökkentésének lépésein a képek mintavételezésével, amikor az Aspose.Words for .NET segítségével PDF-be konvertál. Ez csökkenti a generált PDF fájl méretét. Kövesse az alábbi lépéseket:

## 1. lépés: A dokumentum betöltése

Először töltse fel a PDF-be konvertálni kívánt dokumentumot:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Ügyeljen arra, hogy a dokumentum helyes elérési útját adja meg.

## 2. lépés: Konfigurálja a PDF mentési beállításokat

Hozzon létre egy példányt a PdfSaveOptions osztályból, és állítsa be a kép kicsinyítési beállításait:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 A`Resolution` tulajdonság megadja a képek célfelbontását és a`ResolutionThreshold`tulajdonság azt a minimális felbontást adja meg, amely alatt a képek nem kicsinyíthetők.

## 3. lépés: Konvertálja a dokumentumot PDF-be

 Használja a`Save` módszer a dokumentum PDF-be konvertálására, megadva a mentési beállításokat:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Ügyeljen arra, hogy a konvertált PDF mentéséhez a megfelelő útvonalat adja meg.

### Példa forráskódra a képek lemintázásához az Aspose.Words for .NET használatával

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Beállíthatunk egy minimális küszöböt a mintavételezéshez.
	// Ez az érték megakadályozza a bemeneti dokumentum második képének lemintavételét.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Az alábbi lépések követésével könnyedén csökkentheti a képfelbontást, amikor az Aspose.Words for .NET segítségével PDF formátumba konvertál.

## Következtetés

Ebben az oktatóanyagban elmagyaráztuk, hogyan csökkentheti a PDF-dokumentum méretét képmintavételezéssel, amikor az Aspose.Words for .NET használatával PDF-be konvertál. A leírt lépések követésével könnyedén csökkentheti a képek felbontását és a generált PDF fájl méretét. Ügyeljen arra, hogy megadja a dokumentum helyes elérési útját, és szükség szerint konfigurálja a képmintavételi beállításokat. A PDF-fájl méretének csökkentése megkönnyíti a fájlok megosztását, tárolását és gyors betöltését különböző platformokon. Élvezze a PDF-dokumentum méretének csökkentésének előnyeit az Aspose.Words for .NET segítségével képmintavételezéssel.

### Gyakran Ismételt Kérdések

#### K: Mi csökkenti a PDF-dokumentum méretét képmintavételezéssel?
V: A PDF-dokumentum méretének csökkentése az Image Sampling segítségével a létrehozott PDF-fájl méretének csökkentését jelenti a képek felbontásának csökkentésével PDF-be konvertáláskor. Ez optimalizálja a tárhely felhasználását, és megkönnyíti a PDF-fájlok megosztását és átvitelét.

#### K: Hogyan csökkenthetem a PDF-dokumentum méretét képmintavételezéssel az Aspose.Words for .NET használatával?
V: A PDF-dokumentum méretének csökkentéséhez képmintavételezéssel az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:

 Cseréléssel állítsa be a könyvtár elérési útját, ahol a dokumentumok találhatók`"YOUR DOCUMENTS DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

 Töltse be a PDF-be konvertálni kívánt dokumentumot a`Document` osztályt, és adja meg a dokumentum elérési útját a megadott dokumentumok könyvtárban.

 Konfigurálja a mentés PDF-ként opcióit a példány létrehozásával`PdfSaveOptions` osztályt, és a képmintavételi beállításokat a segítségével állítsa be`DownsampleOptions` ingatlan. A képek célfelbontását a gombbal adhatja meg`Resolution` tulajdonságot, és állítson be egy minimális felbontási küszöböt, amely felett a képek nem kicsinyíthetők a használatával`ResolutionThreshold` ingatlan.

 Mentse el a dokumentumot PDF formátumban a`Save` módszere a`Document` osztály, amely megadja az elérési utat és a mentési lehetőségeket.

#### K: Milyen előnyökkel jár a PDF-dokumentum méretének képmintavételezéssel történő csökkentése?
V: A PDF-dokumentum méretének képmintavételezéssel történő csökkentésének előnyei a következők:

Csökkentett PDF-fájlméret: A kép-mintavételezés csökkenti a PDF-dokumentumban lévő képek felbontását, ami jelentősen csökkenti a PDF-fájl méretét. Ez megkönnyíti a fájl megosztását és átvitelét, különösen e-mailben vagy online.

Tárhely optimalizálása: A PDF-fájl méretének csökkentése segít optimalizálni a tárhely felhasználását, különösen akkor, ha sok PDF-fájlja van, amelyek nagy felbontású képeket tartalmaznak.

Teljesítményfejlesztések: A kisebb PDF-fájlok gyorsabban töltődnek be, és gyorsabban nyithatók meg és tekinthetők meg különböző eszközökön.