---
title: Frissítse az utolsó nyomtatott tulajdonságot PDF-dokumentumban
linktitle: Frissítse az utolsó nyomtatott tulajdonságot PDF-dokumentumban
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre az „Utolsó nyomtatás” tulajdonság frissítéséhez, amikor az Aspose.Words for .NET segítségével PDF formátumba konvertál.
type: docs
weight: 10
url: /hu/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Ez a cikk lépésenkénti útmutatót tartalmaz a PDF-dokumentum frissítési funkciójának „Utolsó nyomtatás” tulajdonságának használatához az Aspose.Words for .NET-ben. Részletesen elmagyarázzuk a kód minden részét. Ennek az oktatóanyagnak a végén megtudhatja, hogyan konfigurálhatja az „Utolsó nyomtatás” tulajdonság frissítését a PDF-formátumba konvertáláskor.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette és konfigurálta az Aspose.Words for .NET könyvtárat a projektben. A könyvtárat és a telepítési utasításokat az Aspose webhelyén találja.

## 1. lépés: Határozza meg a dokumentumkönyvtárat

 A kezdéshez meg kell határoznia annak a könyvtárnak az elérési útját, ahol a dokumentumok találhatók. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse fel a dokumentumot

Ezután be kell töltenünk a feldolgozni kívánt dokumentumot. Ebben a példában feltételezzük, hogy a dokumentum neve "Rendering.docx", és a megadott dokumentumkönyvtárban található.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. lépés: Konfigurálja a Mentés PDF-ként opciókat a frissített „Utolsó nyomtatás” tulajdonsággal

 A „Utolsó nyomtatás” tulajdonság frissítésének engedélyezéséhez PDF-be konvertáláskor konfigurálnunk kell a`PdfSaveOptions` objektumot és állítsa be a`UpdateLastPrintedProperty`tulajdonát`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## 4. lépés: Mentse el a dokumentumot PDF formátumban az „Utolsó nyomtatás” tulajdonság frissítésével

Végül elmenthetjük a dokumentumot PDF formátumban a korábban beállított mentési opciókkal.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

Ez minden ! Sikeresen engedélyezte az "Utolsó nyomtatás" tulajdonság frissítését, amikor egy dokumentumot PDF-formátumba konvertál az Aspose.Words for .NET használatával.

### Példa forráskód az "Utoljára nyomtatott" tulajdonság frissítéséhez az Aspose.Words .NET-hez


```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## Következtetés

Ebben az oktatóanyagban elmagyaráztuk, hogyan frissítheti a "Utoljára nyomtatott" tulajdonságot egy PDF-dokumentumban az Aspose.Words for .NET használatával. A megadott lépések követésével egyszerűen konfigurálhatja az „Utolsó nyomtatás” tulajdonság frissítésének lehetőségét, amikor egy dokumentumot PDF formátumba konvertál. Ezzel a funkcióval nyomon követheti a dokumentumhasználatot és a kapcsolódó információkat.

### Gyakran Ismételt Kérdések

#### K: Mi az „Utoljára nyomtatott” tulajdonság egy PDF-dokumentumban?
V: A PDF-dokumentum "Utolsó nyomtatása" tulajdonsága a dokumentum utolsó nyomtatásának dátumára és időpontjára vonatkozik. Ez a tulajdonság hasznos lehet a dokumentumhasználattal és -kezeléssel kapcsolatos információk nyomon követéséhez.

#### K: Hogyan frissíthetem az "Utoljára nyomtatott" tulajdonságot egy PDF-dokumentumban az Aspose.Words for .NET segítségével?
V: A PDF-dokumentum "Utolsó nyomtatása" tulajdonságának Aspose.Words for .NET használatával frissítéséhez kövesse az alábbi lépéseket:

 Hozzon létre egy példányt a`Document` osztály, amely megadja a Word dokumentum elérési útját.

 Hozzon létre egy példányt a`PdfSaveOptions` osztályt, és állítsa be a`UpdateLastPrintedProperty`tulajdonát`true` az "Utolsó nyomtatás" tulajdonság frissítésének engedélyezéséhez.

 Használja a`Save` módszere a`Document`osztályba, hogy a dokumentumot PDF formátumba mentse a mentési beállítások megadásával.

#### K: Hogyan ellenőrizhetem, hogy az "Utolsó nyomtatás" tulajdonság frissült-e a létrehozott PDF dokumentumban?
V: Ellenőrizheti, hogy az „Utolsó nyomtatás” tulajdonság frissült-e a létrehozott PDF-dokumentumban, ha megnyitja a PDF-fájlt egy kompatibilis PDF-megtekintővel, például az Adobe Acrobat Readerrel, és megtekinti a dokumentum adatait. Az utolsó nyomtatás dátumának és időpontjának meg kell egyeznie a PDF dokumentum generálásának dátumával és időpontjával.
