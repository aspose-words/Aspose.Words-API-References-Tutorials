---
title: Tartsa meg a régi vezérlőkaraktereket
linktitle: Tartsa meg a régi vezérlőkaraktereket
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan őrizheti meg a régi vezérlőkaraktereket, amikor egy dokumentumot ment az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

Ebben az oktatóanyagban megvizsgáljuk a mellékelt C# forráskódot, hogy megőrizzük a régi vezérlőkaraktereket, amikor egy dokumentumot Aspose.Words for .NET használatával mentünk. Ez a funkció lehetővé teszi a speciális vezérlőkarakterek megőrzését dokumentum konvertálásakor vagy mentésekor.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy beállította fejlesztői környezetét az Aspose.Words for .NET segítségével. Győződjön meg arról, hogy hozzáadta a szükséges hivatkozásokat, és importálta a megfelelő névtereket.

## 2. lépés: A dokumentum betöltése

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 Ebben a lépésben a dokumentumot a`Document` metódust, és átadja az örökölt vezérlőkaraktereket tartalmazó fájl elérési útját.

## 3. lépés: Az OOXML biztonsági mentési beállításainak konfigurálása

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

 Ebben a lépésben konfiguráljuk az OOXML mentési beállításait egy új létrehozásával`OoxmlSaveOptions` tárgy. Megadjuk a kívánt mentési formátumot (itt,`FlatOpc` ), és engedélyezze a`KeepLegacyControlChars` lehetőség az örökölt vezérlőkarakterek megtartására.

## 4. lépés: A dokumentum mentése örökölt vezérlőkarakterekkel

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 Az utolsó lépésben a dokumentumot a`Save` metódust, és átadja a kimeneti fájl elérési útját a`.docx` kiterjesztést, a megadott mentési beállításokkal együtt.

Mostantól a forráskód futtatásával megőrizheti a régi vezérlőkaraktereket a dokumentum mentésekor. Az eredményül kapott fájl a megadott könyvtárba kerül mentésre „WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx” néven.

### Minta forráskód a Keep Legacy Control Chars alkalmazáshoz az Aspose.Words for .NET használatával 
```csharp

// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk a régi vezérlőkarakterek megőrzésének funkcióit egy dokumentum Aspose.Words for .NET használatával mentésekor. Megtanultuk, hogyan kell megőrizni azokat a speciális karaktereket, amelyek fontosak lehetnek a dokumentum megfelelő formázásához vagy megjelenítéséhez.

 Az örökölt vezérlőkarakterek megőrzése különösen hasznos olyan dokumentumoknál, amelyek régebbi vagy speciális szolgáltatásokat, például speciális vezérlőkaraktereket használnak. Engedélyezésével a`KeepLegacyControlChars` opcióval a dokumentum mentésekor gondoskodik ezeknek a karaktereknek a megőrzéséről.

Az Aspose.Words for .NET rugalmas és hatékony biztonsági mentési lehetőségek széles skáláját kínálja a dokumentumkezelési igények kielégítésére. A megfelelő opciók használatával testreszabhatja a biztonsági mentési folyamatot, hogy megőrizze a dokumentumok sajátos jellemzőit.

Nyugodtan építse be ezt a funkciót Aspose.Words for .NET projektjébe, hogy biztosítsa a dokumentumaiban lévő örökölt vezérlőkarakterek integritását és megőrzését.