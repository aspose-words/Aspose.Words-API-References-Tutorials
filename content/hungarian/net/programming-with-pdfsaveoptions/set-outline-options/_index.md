---
title: Állítsa be a vázlatbeállításokat egy PDF-dokumentumban
linktitle: Állítsa be a vázlatbeállításokat egy PDF-dokumentumban
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a vázlatbeállítások megadásához PDF-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-pdfsaveoptions/set-outline-options/
---

Ez a cikk lépésről lépésre ismerteti, hogyan használhatja a beállított vázlatbeállításokat a metafájlméret funkcióhoz az Aspose.Words for .NET-ben. Részletesen elmagyarázzuk a kód minden részét. Az oktatóanyag végén megtudhatja, hogyan állíthat be vázlatbeállításokat egy dokumentumban, és hogyan hozhat létre PDF-et a megfelelő vázlatbeállításokkal.

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

## 3. lépés: Konfigurálja a mentés PDF-ként opciókat a tervbeállításokkal

 A generált PDF-ben a vázlatbeállítások beállításához konfigurálnunk kell a`PdfSaveOptions` tárgy. Beállíthatjuk a címsorvázlat szintek számát (`HeadingsOutlineLevels`) és a kibontott körvonalszintek száma (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## 4. lépés: Mentse el a dokumentumot PDF formátumban a vázlat opciókkal

Végül elmenthetjük a dokumentumot PDF formátumban a korábban beállított mentési opciókkal.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

Ez minden ! Sikeresen beállította a vázlatbeállításokat egy dokumentumban, és az Aspose.Words for .NET segítségével PDF-et hozott létre a megfelelő vázlatbeállításokkal.

### Példa forráskódra a tervbeállítások metafájl méretének beállításához az Aspose.Words for .NET segítségével


```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## Következtetés

Ebben az oktatóanyagban elmagyaráztuk, hogyan állíthat be vázlatbeállításokat egy PDF-dokumentumban az Aspose.Words for .NET használatával. A leírt lépések segítségével egyszerűen megadhatja a címsor és a vázlat szintjeit a dokumentumban, és létrehozhat egy PDF-fájlt a megfelelő vázlatopciókkal. Az Aspose.Words for .NET használatával javíthatja a PDF-dokumentumok szerkezetét és navigálását az vázlat opció előnyeit.

### Gyakran Ismételt Kérdések

#### K: Mi a vázlat opció egy PDF-dokumentumban?
V: A PDF-dokumentumban a vázlat opció a dokumentum tartalmának hierarchikus szerkezetére utal. Lehetővé teszi interaktív tartalomjegyzék létrehozását, és megkönnyíti a navigációt a dokumentumban. A vázlatbeállítások határozzák meg a vázlatban szereplő cím- és feliratszinteket, valamint a generált vázlatban megjelenítendő részletezési szintet.

#### K: Hogyan állíthatok be vázlatbeállításokat egy PDF-dokumentumban az Aspose.Words for .NET használatával?
V: Az Aspose.Words for .NET használatával PDF-dokumentumban a vázlatbeállítások megadásához kövesse az alábbi lépéseket:

 Cseréléssel állítsa be a könyvtár elérési útját, ahol a dokumentumok találhatók`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

 Töltse be a PDF-be konvertálni kívánt dokumentumot a`Document` osztályt, és adja meg a dokumentum elérési útját a megadott dokumentumok könyvtárban.

 Konfigurálja a mentés PDF-ként opcióit a példány létrehozásával`PdfSaveOptions` osztályban és a`OutlineOptions` tulajdonságot a vázlatbeállítások beállításához. A vázlatban szereplő címsorszintek számát a gombbal adhatja meg`HeadingsOutlineLevels` tulajdonság és a kiterjesztett körvonalszintek száma a segítségével`ExpandedOutlineLevels` ingatlan.

 Mentse el a dokumentumot PDF formátumban a`Save` módszere a`Document` osztály, amely megadja az elérési utat és a mentési lehetőségeket.

#### K: Mi a terv opció egy PDF-dokumentumban?
V: A PDF-dokumentumban található vázlat opció lehetővé teszi a tartalom hierarchikus szerkezetének létrehozását, amely megkönnyíti a dokumentumban való navigálást és a különböző szakaszok elérését. Ez lehetővé teszi a felhasználók számára, hogy a tartalomjegyzék vagy a vázlat bejegyzéseire kattintva gyorsan a dokumentum adott részeire ugorjanak. A vázlat opció az olvasási élményt is javítja azáltal, hogy áttekintést nyújt a dokumentum általános szerkezetéről.
