---
title: Dokumentum szövegének iránya
linktitle: Dokumentum szövegének iránya
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan adhat meg szövegirányt a dokumentumokban az Aspose.Words for .NET segítségével. A jobbról balra író nyelvek megjelenítésének javítása.
type: docs
weight: 10
url: /hu/net/programming-with-txtloadoptions/document-text-direction/
---

Ebben az oktatóanyagban az Aspose.Words for .NET-hez tartozó „Dokumentumszöveg-irány” funkcióhoz biztosított C#-forráskódot fogjuk felfedezni. Ez a funkció lehetővé teszi a szöveg irányának megadását a dokumentumban, ami különösen hasznos a jobbról balra írt nyelveknél, például héberül vagy arabul.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy beállította fejlesztői környezetét az Aspose.Words for .NET segítségével. Győződjön meg arról, hogy hozzáadta a szükséges hivatkozásokat, és importálta a megfelelő névtereket.

## 2. lépés: A feltöltési beállítások konfigurálása

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 Ebben a lépésben konfiguráljuk a dokumentumbetöltési beállításokat. Létrehozunk egy újat`TxtLoadOptions` objektumot és állítsa be a`DocumentDirection`tulajdonát`DocumentDirection.Auto`. Ez az érték utasítja az Aspose.Words-t, hogy automatikusan határozza meg a szöveg irányát a dokumentum tartalma alapján.

## 3. lépés: A dokumentum betöltése

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 Ebben a lépésben a dokumentumot a`Document` metódust, és átadja a betöltendő szövegfájl elérési útját. A megadott rakodási lehetőségeket is használjuk.

## 4. lépés: Manipulálja a bekezdést, és jelenítse meg a szöveg irányát

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 Ebben a lépésben elérjük a dokumentum első bekezdését a`FirstSection` és`Body` tulajdonságait. Ezután elérjük a`ParagraphFormat.Bidi` tulajdonság a bekezdés szövegirányának lekéréséhez. Ezután megjelenítjük ezt az értéket a konzolon.

## 5. lépés: Mentse el a dokumentumot

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 Ebben az utolsó lépésben az eredményül kapott dokumentumot .docx formátumban mentjük a`Save` módszert, és átadja a kimeneti fájl elérési útját.

Most már futtathatja a forráskódot a szöveges dokumentum betöltéséhez és a szöveg irányának meghatározásához. Az eredményül kapott dokumentumot a rendszer a megadott könyvtárba menti "WorkingWithTxtLoadOptions.DocumentTextDirection.docx" néven.

### Forráskód minta a dokumentumszöveg-irányító funkciókhoz az Aspose.Words for .NET segítségével.


```csharp

            
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk az Aspose.Words for .NET dokumentumszöveg-irányító funkcióját. Megtanultuk, hogyan kell megadni a szöveg irányát egy dokumentumban, különösen a jobbról balra írt nyelveknél, például héberül vagy arabul.

Ez a funkció elengedhetetlen annak biztosításához, hogy a szöveg helyesen jelenjen meg a többnyelvű dokumentumokban. A megfelelő betöltési beállítások használatával az Aspose.Words automatikusan felismeri a szöveg irányát, és alkalmazza azt a dokumentumra.

Az Aspose.Words segítségével könnyedén módosíthatja a szövegek irányát a dokumentumokban, így gördülékeny és intuitív olvasási élményt nyújt a felhasználók számára.

Fontos megjegyezni, hogy ez a funkció különösen akkor hasznos, ha olyan nyelvekkel dolgozunk, amelyek speciális szövegirányt igényelnek. Az Aspose.Words megkönnyíti ezt a feladatot, mivel hatékony eszközöket biztosít a szövegek irányának kezelésére a dokumentumokban.

Ne felejtse el használni a megfelelő betöltési beállításokat, például az automatikus szövegirány beállítását, hogy elérje a kívánt eredményt a dokumentumokban.

Az Aspose.Words for .NET számos fejlett szolgáltatást kínál a dokumentumok kezeléséhez és létrehozásához. Az Aspose.Words által biztosított dokumentáció és példák további tanulmányozásával teljes mértékben kiaknázhatja ennek a nagy teljesítményű könyvtárnak a lehetőségeit.

Tehát ne habozzon integrálni a dokumentumszöveg-irányt az Aspose.Words for .NET projektjébe, és kihasználja annak előnyeit vonzó és jó minőségű többnyelvű dokumentumok létrehozásához.