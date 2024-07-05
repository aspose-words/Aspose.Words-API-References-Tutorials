---
title: Egyéni tulajdonságok exportálása PDF-dokumentumban
linktitle: Egyéni tulajdonságok exportálása PDF-dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan exportálhat egyéni tulajdonságokat dokumentumok PDF-formátumba konvertálásakor az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-pdfsaveoptions/custom-properties-export/
---

Ebben az oktatóanyagban végigvezetjük a dokumentum egyéni tulajdonságainak PDF-dokumentumba történő exportálásához az Aspose.Words for .NET használatával. Az egyéni tulajdonságok exportálása lehetővé teszi további információk felvételét a létrehozott PDF dokumentumba. Kövesse az alábbi lépéseket:

## 1. lépés: Dokumentum létrehozása és egyéni tulajdonságok hozzáadása

Kezdje a Dokumentum osztály példányának létrehozásával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2. lépés: Adjon hozzá egyéni tulajdonságokat
 Ezután adja hozzá a kívánt egyéni tulajdonságokat. Például egy "Cég" tulajdonság "Aspose" értékű hozzáadásához használja a`Add` a CustomDocumentProperties gyűjtemény metódusa:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Tetszőleges számú egyéni tulajdonságot adhat hozzá.

## 3. lépés: Állítsa be a PDF-exportálási beállításokat

Hozzon létre egy példányt a PdfSaveOptions osztályból, és adja meg az egyéni tulajdonságok exportálásának módját:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Ez a beállítás szabályozza az egyéni tulajdonságok exportálását PDF-be konvertáláskor.

## 4. lépés: Konvertálja a dokumentumot PDF-be

 Használja a`Save` módszer a dokumentum PDF-be konvertálására, megadva a konvertálási beállításokat:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Ügyeljen arra, hogy a konvertált PDF mentéséhez a megfelelő útvonalat adja meg.

### Példa forráskód az egyéni tulajdonságok exportálásához az Aspose.Words for .NET használatával

Itt található a teljes forráskód az egyéni tulajdonságok exportálásához egy dokumentumból az Aspose.Words for .NET használatával:


```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Az alábbi lépések követésével könnyedén exportálhatja a dokumentumok egyéni tulajdonságait, amikor az Aspose.Words for .NET segítségével PDF formátumba konvertál.


## Következtetés

Ebben az oktatóanyagban elmagyaráztuk, hogyan exportálhat egyéni tulajdonságokat egy dokumentumból PDF dokumentumba az Aspose.Words for .NET használatával. A leírt lépések követésével könnyedén beilleszthet további információkat a létrehozott PDF dokumentumba a dokumentum egyéni tulajdonságainak exportálásával. Használja ki az Aspose.Words for .NET szolgáltatásait a PDF-dokumentumok személyre szabásához és gazdagításához egyéni tulajdonságok exportálásával.

### Gyakran Ismételt Kérdések

#### K: Mit jelent az egyéni tulajdonságok exportálása PDF dokumentumba?
V: Az egyéni tulajdonságok PDF-dokumentumba történő exportálása lehetővé teszi további információk felvételét a létrehozott PDF-dokumentumba. Az egyéni tulajdonságok a dokumentumra jellemző metaadatok, például címkék, kulcsszavak vagy hitelesítő adatok. Ezen egyéni tulajdonságok exportálásával elérhetővé teheti őket a felhasználók számára a PDF-dokumentum megtekintésekor.

#### K: Hogyan exportálhatom egy dokumentum egyéni tulajdonságait PDF dokumentumba az Aspose.Words for .NET használatával?
V: Ha egy dokumentum egyéni tulajdonságait PDF-dokumentumba szeretné exportálni az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:

 Hozzon létre egy példányt a`Document` osztály.

 Adja hozzá a kívánt egyéni tulajdonságokat a`CustomDocumentProperties` Gyűjtemény. Például használja a`Add` módszerrel hozzáadhat egy „Vállalat” tulajdonságot „Aspose” értékkel.

 Hozzon létre egy példányt a`PdfSaveOptions` osztályt, és adja meg, hogyan exportáljon egyéni tulajdonságokat a`CustomPropertiesExport` ingatlan. A`PdfCustomPropertiesExport.Standard` érték exportálja az egyéni tulajdonságokat az alapértelmezett beállításoknak megfelelően.

 Használja a`Save` módszere a`Document` osztályt a dokumentum PDF formátumba konvertálásához, megadva az átalakítási beállításokat.

#### K: Hogyan férhetek hozzá egy PDF-dokumentum egyéni tulajdonságaihoz?
V: A PDF-dokumentumok egyéni tulajdonságainak eléréséhez használhat egy kompatibilis PDF-olvasót, amely támogatja a dokumentum tulajdonságainak megtekintését. A legtöbb elterjedt PDF-olvasó, például az Adobe Acrobat Reader hozzáférést biztosít a PDF-dokumentumok metaadataihoz és tulajdonságaihoz. Ezeket a beállításokat általában a "Fájl" menüben találja meg, vagy kattintson a jobb gombbal a dokumentumra, és válassza a "Tulajdonságok" lehetőséget.