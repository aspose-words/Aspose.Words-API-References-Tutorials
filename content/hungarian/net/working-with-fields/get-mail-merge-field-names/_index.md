---
title: Kérje le a körlevél mezőneveket
linktitle: Kérje le a körlevél mezőneveket
second_title: Aspose.Words Document Processing API
description: Az Aspose.Words for .NET segítségével megtudhatja, hogyan töltheti be a körlevél-mezőneveket Word-dokumentumaiba.
type: docs
weight: 10
url: /hu/net/working-with-fields/get-mail-merge-field-names/
---

Íme egy lépésről lépésre bemutatott útmutató az alábbi C# forráskód magyarázatához, amely az Aspose.Words for .NET "Get Merge Field Names" funkcióját használja. A kívánt eredmény elérése érdekében gondosan kövesse az egyes lépéseket.

## 1. lépés: Dokumentumkönyvtár beállítása

A megadott kódban meg kell adnia dokumentumai könyvtárát. Cserélje le a „DOKUMENTUMKÖNYVTÁR” értéket a dokumentumkönyvtár megfelelő elérési útjára.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: A dokumentum betöltése

Első lépésként töltse be azt a dokumentumot, ahonnan az egyesítési mezők neveit szeretné lekérni.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Feltétlenül cserélje ki a „DOKUMENTUMFÁJL” elemet a saját fájl nevére.

## 3. lépés: Szerezzen be egyesítési mezőneveket

 Használjuk a`GetFieldNames()` metódussal kap egy tömböt, amely a dokumentumban található egyesítési mezők neveit tartalmazza.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 A`fieldNames` változó mostantól tartalmazza az egyesítési mezők nevét.

### Forráskód-példa az Aspose.Words .NET-hez tartozó egyesített mezőnevek lekéréséhez

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Egyesítési mezőnevek lekérése.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Az egyesítési mezők számának megjelenítése.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 Ebben a példában betöltöttünk egy dokumentumot, és az összevonási mezők neveit a`GetFieldNames()` módszert, és megjelenítette a dokumentumban található egyesítési mezők számát.

Ezzel véget is értünk az Aspose.Words for .NET-hez készült "Get Merge Field Names" funkció használatáról szóló útmutatónkat.

### GYIK

#### 1. kérdés: Mi az a körlevél az Aspose.Words programban?

Az Aspose.Words levelezőegyesítése egy olyan folyamat, amely külső forrásból (pl. Excel-táblázatból vagy adatbázisból) származó adatokat egyesít egy Word-dokumentum sablonnal, így személyre szabott dokumentumokat hozhat létre. Ez megkönnyíti a levelek, jelentések és más hasonló dokumentumok automatikus generálását.

#### 2. kérdés: Hogyan kaphatom meg a Word-dokumentumban elérhető körlevél-mezők listáját?

A Word-dokumentumban elérhető körlevél-mezők listájának megtekintéséhez kövesse az alábbi lépéseket:

1. Importálja a Document és MailMergeFieldNames osztályokat az Aspose.Words névtérből.
2. Hozzon létre egy dokumentumpéldányt a Word-dokumentum betöltésével.
3. Használja a Dokumentum objektum GetMailMergeFieldNames metódusát az elérhető körlevél-mezők listájának lekéréséhez.

Íme egy mintakód a folyamat szemléltetésére:

```csharp
// Importálja a szükséges névtereket
using Aspose.Words;
using Aspose.Words.MailMerging;

// Töltse be a meglévő dokumentumot
Document document = new Document("FilePath");

// Lekérheti a körlevél mezők listáját
MailMergeFieldNames fieldNames = document.MailMerge.GetFieldNames();

// Váltson végig az elérhető körlevél-mezőkön
foreach (string fieldName in fieldNames)
{
     // Csináljon valamit a mező nevével
     Console.WriteLine(fieldName);
}
```
### GYIK

#### K: Mi az a körlevél az Aspose.Words programban?

V: Az Aspose.Words körlevél-összevonása egy olyan folyamat, amely külső forrásból (pl. Excel-táblázatból vagy adatbázisból) származó adatokat egyesít egy Word dokumentumsablonnal, így személyre szabott dokumentumokat hozhat létre. Ez megkönnyíti a levelek, jelentések és más hasonló dokumentumok automatikus generálását.

#### K: Hogyan kaphatom meg a Word-dokumentumban elérhető körlevél-mezők listáját?

V: A Word-dokumentumban elérhető körlevél-mezők listájának megtekintéséhez kövesse az alábbi lépéseket:

1. Importálja a Document és MailMergeFieldNames osztályokat az Aspose.Words névtérből.
2. Hozzon létre egy dokumentumpéldányt a Word-dokumentum betöltésével.
3. Használja a Dokumentum objektum GetMailMergeFieldNames metódusát az elérhető körlevél-mezők listájának lekéréséhez.

#### K: Kaphatok-e körlevél-mezőket külső adatforrásból, például Excel-táblázatból?

V: Igen, lekérheti a körlevél mezőket külső adatforrásból, például Excel-táblázatból. Ehhez használhatja az Aspose.Words adat-összerendelési szolgáltatásait, hogy kapcsolatot létesítsen az adatforrással, és lekérje az elérhető mezők nevét.

#### K: Lehetséges-e bizonyos kritériumok alapján szűrni a körlevél-mezőket?

V: Igen, lehetséges a körlevél mezők szűrése bizonyos kritériumok alapján. Használhat reguláris kifejezéseket vagy speciális feltételeket a körlevél-mezők szűrésére, és csak azokat kaphatja meg, amelyek megfelelnek az adott feltételeknek.

#### K: Hogyan kezelhetem az Aspose.Words körlevél-egyesítési mezőit?

V: Az Aspose.Words körlevél-mezőinek kezeléséhez használhatja a Document és MailMergeField objektumok által biztosított metódusokat és tulajdonságokat. Hozzáadhat, eltávolíthat vagy frissíthet körlevél-mezőket, valamint lekérheti és szerkesztheti a mezőkkel társított értékeket.