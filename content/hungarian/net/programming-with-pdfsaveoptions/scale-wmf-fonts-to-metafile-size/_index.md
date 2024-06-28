---
title: Csökkentse a PDF méretét a Wmf betűtípusok átméretezésével metafájl méretre
linktitle: Csökkentse a PDF méretét a Wmf betűtípusok átméretezésével metafájl méretre
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a PDF méretének csökkentéséhez wmf betűtípusok átméretezésével metafájl méretre, ha az Aspose.Words for .NET segítségével PDF formátumba konvertál.
type: docs
weight: 10
url: /hu/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Ez a cikk lépésről lépésre ismerteti, hogyan csökkentheti a pdf méretét wmf betűtípusok metafájlméretre skálázásával az Aspose.Words for .NET segítségével. Részletesen elmagyarázzuk a kód minden részét. Ennek az oktatóanyagnak a végén megtudhatja, hogyan engedélyezheti vagy tilthatja le a WMF betűtípus-méretezést PDF-formátumba konvertálásakor.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette és konfigurálta az Aspose.Words for .NET könyvtárat a projektben. A könyvtárat és a telepítési utasításokat az Aspose webhelyén találja.

## 1. lépés: Határozza meg a dokumentumkönyvtárat

 A kezdéshez meg kell határoznia annak a könyvtárnak az elérési útját, ahol a dokumentumok találhatók. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse fel a dokumentumot

Ezután be kell töltenünk a feldolgozni kívánt dokumentumot. Ebben a példában feltételezzük, hogy a dokumentum neve "WMF with text.docx", és a megadott dokumentumkönyvtárban található.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## 3. lépés: Konfigurálja a metafájl-megjelenítési beállításokat

 A WMF-betűkészlet metafájl méretre való átméretezésének engedélyezéséhez vagy letiltásához konfigurálnunk kell a`MetafileRenderingOptions` tárgy. Ebben a példában letiltjuk a betűméretezést a`ScaleWmfFontsToMetafileSize`tulajdonát`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## 4. lépés: Konfigurálja a mentés PDF-ként opciókat a metafájl-megjelenítési beállításokkal

Végül konfigurálhatjuk a PDF-be mentés opciókat a korábban beállított metafájl megjelenítési beállításokkal.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## 5. lépés: Mentse el a dokumentumot PDF formátumban a metafile rendering opciókkal

Mentse el a dokumentumot PDF formátumban a korábban beállított mentési beállításokkal.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Ez minden ! Sikeresen engedélyezte vagy letiltotta a WMF-betűkészlet metafájl méretre skálázását konvertáláskor

PDF dokumentum az Aspose.Words for .NET használatával.

### Példa forráskódra a WMF-betűkészletek metafájl méretre skálázásához az Aspose.Words for .NET segítségével

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	//Ha az Aspose.Words nem tudja megfelelően megjeleníteni a metafájl rekordok egy részét vektorgrafikus formátumban
	// majd az Aspose.Words ezt a metafájlt bittérképpé teszi.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Következtetés

Ebben az oktatóanyagban elmagyaráztuk, hogyan lehet engedélyezni vagy letiltani a WMF-betűkészletek átméretezését metafájl méretűre egy PDF-dokumentumban az Aspose.Words for .NET használatával. A leírt lépések követésével könnyedén szabályozhatja, hogy a WMF-betűtípusokat át kell-e méretezni, hogy azok megfeleljenek a metafájl méretének, amikor PDF-dokumentummá konvertálja. Ezzel csökkentheti a generált PDF-fájl méretét, és javíthatja a renderelési teljesítményt. Ügyeljen arra, hogy megadja a dokumentumok helyes elérési útját, és szükség szerint konfigurálja a metafájl megjelenítési beállításait.

### Gyakran Ismételt Kérdések

#### K: Mit jelent a WMF betűtípusok átméretezése metafájl méretre egy PDF dokumentumban?
V: A WMF-betűtípusok átméretezése a PDF-dokumentumban lévő metafájl méretére egy olyan szolgáltatás, amely szabályozza, hogy a WMF-betűtípusokat a PDF-dokumentummá konvertáláskor a metafájl méretéhez kell-e méretezni. Ha ez a funkció engedélyezve van, a WMF-betűkészletek a metafájl méretéhez igazodnak, ami csökkentheti a létrehozott PDF-dokumentum méretét.

#### K: Hogyan használhatom az Aspose.Words for .NET alkalmazást a WMF-betűtípusok metafájl méretűre való átméretezésének engedélyezésére vagy letiltására egy PDF-dokumentumban?
V: A WMF-betűkészletek metafájl-méretre való átméretezésének engedélyezéséhez vagy letiltásához PDF-dokumentumban az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:

 Cseréléssel állítsa be a könyvtár elérési útját, ahol a dokumentumok találhatók`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

 Töltse be a feldolgozni kívánt dokumentumot a`Document` osztályt, és adja meg a Word dokumentum elérési útját a megadott dokumentumok könyvtárban.

 Konfigurálja a metafájl megjelenítési beállításait a példány létrehozásával`MetafileRenderingOptions` osztály és beállítás a`ScaleWmfFontsToMetafileSize`tulajdonát`true` a WMF betűtípusok metafájl méretre vagy méretre skálázásának engedélyezéséhez`false` a funkció letiltásához.

 Konfigurálja a mentés PDF-ként opcióit a példány létrehozásával`PdfSaveOptions` osztályban, és a korábban beállított metafájl-megjelenítési beállításokat használja.

 Mentse el a dokumentumot PDF formátumban a`Save` módszere a`Document` osztály, amely megadja az elérési utat és a mentési lehetőségeket.

#### K: Milyen előnyökkel jár a WMF-betűtípusok metafájlméretre való átméretezése egy PDF-dokumentumban?
V: A WMF betűtípusok metafájl méretűre átméretezésének előnyei a PDF-dokumentumban:

PDF-fájl méretének csökkentése: A WMF-betűtípusok átméretezése metafájl méretére csökkentheti a generált PDF-dokumentum méretét azáltal, hogy a betűméretet a metafájl igényeihez igazítja.

Jobb teljesítmény: A WMF betűtípusok méretének a metafájl méretéhez igazításával a PDF-dokumentum megjelenítése gyorsabb és hatékonyabb lehet.