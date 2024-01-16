---
title: Kezelje a Spaces opciókat
linktitle: Kezelje a Spaces opciókat
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan kezelheti a TXT-dokumentumok szóközeit az Aspose.Words for .NET segítségével. Távolítsa el a felesleges szóközöket és javítsa az olvashatóságot.
type: docs
weight: 10
url: /hu/net/programming-with-txtloadoptions/handle-spaces-options/
---

Ebben az oktatóanyagban az Aspose.Words for .NET segítségével a "Térek kezelése TXT betöltési beállításokkal" funkcióhoz biztosított C# forráskódot fogjuk felfedezni. Ez a funkció lehetővé teszi a szóközök kezelési viselkedésének megadását TXT-dokumentum betöltésekor.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy beállította fejlesztői környezetét az Aspose.Words for .NET segítségével. Győződjön meg arról, hogy hozzáadta a szükséges hivatkozásokat, és importálta a megfelelő névtereket.

## 2. lépés: A szöveges dokumentum létrehozása

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

const string textDoc = "Line 1\n" +
                        "Line 2\n" +
                        "Line 3";
```

Ebben a lépésben létrehozunk egy szöveges karakterláncot, amely egy olyan szöveges dokumentumot szimulál, amely sorokat tartalmaz kezdő és záró szóközökkel.

## 3. lépés: A feltöltési beállítások konfigurálása

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions
{
     LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
     TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};
```

 Ebben a lépésben konfiguráljuk a TXT dokumentum betöltésének beállításait. Létrehozunk egy újat`TxtLoadOptions` objektumot és állítsa be a`LeadingSpacesOptions` és`TrailingSpacesOptions` tulajdonságait`TxtLeadingSpacesOptions.Trim` és`TxtTrailingSpacesOptions.Trim` illetőleg. Ez arra utasítja az Aspose.Words-t, hogy a dokumentum betöltésekor távolítsa el a sorok kezdő és záró szóközeit.

## 4. lépés: A dokumentum betöltése

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

 Ebben a lépésben a dokumentumot a`Document` metódust, és átadja a megadott szöveges karakterláncot és betöltési opciókat tartalmazó memóriafolyamot.

## 5. lépés: Mentse el a dokumentumot

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
```

 Ebben az utolsó lépésben az eredményül kapott dokumentumot .docx formátumban mentjük a`Save` módszert, és átadja a kimeneti fájl elérési útját.

Most már futtathatja a forráskódot a szöveges dokumentum betöltéséhez a szóközkezelési beállítások megadásával. Az eredményül kapott dokumentumot a rendszer a megadott könyvtárba menti "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx" néven.

### Minta forráskód a TXT betöltési lehetőségekkel rendelkező Space Management szolgáltatáshoz az Aspose.Words for .NET-hez*

```csharp

            
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

const string textDoc = "      Line 1 \n" +
					   "    Line 2   \n" +
					   " Line 3       ";

TxtLoadOptions loadOptions = new TxtLoadOptions
{
	LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
	TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx")
            
        
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk a terek kezelésének funkcionalitását az Aspose.Words for .NET TXT betöltési lehetőségeivel. Megtanultuk, hogyan lehet megadni a szóközkezelési viselkedést TXT-dokumentum betöltésekor.

Ez a funkció nagyon hasznos a dokumentumban a sorok bal és jobb oldalán lévő felesleges szóközök kezelésére. A megfelelő betöltési beállítások konfigurálásával könnyedén eltávolíthatja ezeket a nem kívánt helyeket, ami segít tisztábbá és olvashatóbbá tenni a dokumentum tartalmát.

Az Aspose.Words for .NET számos fejlett szolgáltatást kínál a dokumentumok kezeléséhez és létrehozásához. A szóközök kezelése TXT-dokumentum betöltésekor az egyike a sok hatékony eszköznek, amelyet az Ön rendelkezésére bocsát.

 Fontos, hogy az adott forgatókönyvnek leginkább megfelelő területkezelési lehetőségeket válassza ki. Ebben a példában a`Trim`opciók a felesleges szóközök eltávolítására a sor elejéről és végéről. Az Aspose.Words azonban más lehetőségeket is kínál a szóközök megtartására, teljes eltávolítására vagy a jelenlegi állapotuk megtartására.

Ne felejtse el ezeket a beállításokat saját igényeihez és TXT-dokumentumai szerkezetéhez igazítani.

Az Aspose.Words for .NET segítségével könnyedén kezelheti a szóközöket a dokumentumokban, javítva az elrendezés minőségét és a tartalom olvashatóságát.

Tehát ne habozzon integrálni a szóközkezelést a TXT betöltési lehetőségekkel az Aspose.Words for .NET projektjébe, és kihasználja annak előnyeit jól formázott és könnyen olvasható dokumentumok létrehozásához.