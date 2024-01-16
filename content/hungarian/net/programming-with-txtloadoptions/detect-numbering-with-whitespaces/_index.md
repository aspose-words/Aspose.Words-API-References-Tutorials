---
title: Számozás észlelése szóközökkel
linktitle: Számozás észlelése szóközökkel
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan észlelheti a listaszámokat szóközökkel az Aspose.Words for .NET programban. Egyszerűen javíthatja dokumentumai szerkezetét.
type: docs
weight: 10
url: /hu/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
Ebben az oktatóanyagban megvizsgáljuk az Aspose.Words for .NET "számozás észlelése szóközökkel" funkciójához biztosított C# forráskódot. Ez a funkció lehetővé teszi listák észlelését és létrehozását egy szöveges dokumentumból, amely listaszámokat és szóközöket tartalmaz.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy beállította fejlesztői környezetét az Aspose.Words for .NET segítségével. Győződjön meg arról, hogy hozzáadta a szükséges hivatkozásokat, és importálta a megfelelő névtereket.

## 2. lépés: A szöveges dokumentum létrehozása

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

Ebben a lépésben létrehozunk egy szöveges karakterláncot, amely egy listaszámokat és szóközöket tartalmazó szöveges dokumentumot szimulál. Különböző listahatárolókat használunk, például pontot, jobb zárójelet, felsorolásjelet és szóközöket.

## 3. lépés: A feltöltési beállítások konfigurálása

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 Ebben a lépésben konfiguráljuk a dokumentumbetöltési beállításokat. Létrehozunk egy újat`TxtLoadOptions` objektumot és állítsa be a`DetectNumberingWithWhitespaces`tulajdonát`true`. Ez lehetővé teszi, hogy az Aspose.Words felismerje a listaszámokat még akkor is, ha szóközök követik őket.

## 4. lépés: A dokumentum betöltése és mentése

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 Ebben a lépésben betöltjük a dokumentumot a megadott szöveges karakterlánc és betöltési beállítások segítségével. Használjuk a`MemoryStream` a szöveges karakterlánc memóriafolyammá alakításához. Ezután a kapott dokumentumot .docx formátumban mentjük.

### Minta forráskód az Aspose.Words for .NET-hez.

```csharp

            
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Hozzon létre egy egyszerű szöveges dokumentumot karakterlánc formájában, amely részek listákként értelmezhetők.
// Betöltéskor az első három listát mindig észleli az Aspose.Words,
// és a Lista objektumok a betöltés után jönnek létre számukra.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// A negyedik lista, szóközzel a lista száma és a listaelem tartalma között,
// csak akkor észlelhető listaként, ha egy LoadOptions objektum "DetectNumberingWithWhitespaces" értéke igaz,
// hogy elkerüljük, hogy a számokkal kezdődő bekezdések tévesen listákként jelenjenek meg.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Töltse be a dokumentumot a LoadOptions paraméterként történő alkalmazása közben, és ellenőrizze az eredményt.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Most futtathatja a forráskódot a listaszámokat és szóközöket tartalmazó szöveges dokumentum betöltéséhez, majd létrehozhat egy .docx dokumentumot az észlelt listákkal. A kimeneti fájl a megadott könyvtárba kerül mentésre "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx" néven.

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk az Aspose.Words for .NET szóközök számozási funkcióját. Megtanultuk, hogyan lehet listákat készíteni egy szöveges dokumentumból, amely listaszámokat és szóközöket tartalmaz.

Ez a funkció rendkívül hasznos a különböző módon formázott listaszámokat tartalmazó dokumentumok feldolgozásához. A megfelelő betöltési opciók használatával az Aspose.Words képes felismerni ezeket a listaszámokat, még akkor is, ha szóközök követik őket, és strukturált listákká alakítja át a végleges dokumentumban.

funkció használatával időt takaríthat meg, és javíthatja a munkafolyamat hatékonyságát. Könnyedén kinyerhet információkat a szöveges dokumentumokból, és megfelelő listákkal jól strukturált dokumentumokká alakíthatja azokat.

A kívánt eredmény elérése érdekében ne felejtse el fontolóra venni a betöltési lehetőségeket, például a szóköztárcsázás érzékelésének konfigurálását.

Az Aspose.Words for .NET számos fejlett szolgáltatást kínál a dokumentumok kezeléséhez és létrehozásához. Az Aspose.Words által biztosított dokumentáció és példák további tanulmányozásával teljes mértékben kiaknázhatja ennek a nagy teljesítményű könyvtárnak a lehetőségeit.

Tehát ne habozzon integrálni a szóközök számozását az Aspose.Words for .NET projektjébe, és kihasználja előnyeit jól strukturált és olvasható dokumentumok létrehozásához.


