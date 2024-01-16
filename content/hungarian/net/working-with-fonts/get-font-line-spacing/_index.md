---
title: Szerezze be a betűtípus sorközt
linktitle: Szerezze be a betűtípus sorközt
second_title: Aspose.Words Document Processing API
description: Ebből az oktatóanyagból megtudhatja, hogyan állíthat be betűtípus-sortávolságot egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fonts/get-font-line-spacing/
---
Ebben az oktatóanyagban elmondjuk, hogyan állíthatja be a betűtípusok sorközét egy Word-dokumentumban az Aspose.Words könyvtár segítségével a .NET-hez. A betűtípus sortávolsága határozza meg a szövegsorok közötti függőleges teret. Lépésről lépésre segítünk megérteni és megvalósítani a kódot a .NET-projektben.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
- C# programozási nyelv gyakorlati ismerete
- A projektben telepített .NET Aspose.Words könyvtár

## 1. lépés: Hozzon létre egy új dokumentumot és dokumentumgenerátort
 Először is létrehozunk egy új dokumentumot a példányosítással`Document` osztályt és egy dokumentumkészítőt a példányosításával`DocumentBuilder` osztály.

```csharp
// Hozzon létre egy új dokumentumot
Document doc = new Document();

//Hozzon létre egy dokumentumgenerátort
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Konfigurálja a betűtípust
 Ezután konfiguráljuk a betűtípust a`Name` a dokumentumgenerátor tulajdonsága.

```csharp
// Konfigurálja a betűtípust
builder.Font.Name = "Calibri";
```

## 3. lépés: Szöveg hozzáadása a dokumentumhoz
Most a dokumentumgenerátort fogjuk használni, hogy formázott szöveget adjunk a dokumentumhoz.

```csharp
// Szöveg hozzáadása a dokumentumhoz
builder. Writen("qText");
```

## 4. lépés: Szerezze be a betűtípus sortávolságát
 Most elérjük a`Font` tárgya a dokumentum első bekezdésében, és lekéri a értékét`LineSpacing` ingatlan.

```csharp
// Szerezze meg a betűtípus sorközét
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Minta forráskód a Betűtípus-sortávolság beszerzéséhez az Aspose.Words for .NET használatával 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Következtetés
Ebben az oktatóanyagban azt láthattuk, hogyan állíthatja be a betűtípusok sorközét egy Word-dokumentumban az Aspose.Words for .NET segítségével. A betűtípus sorköze fontos a szövegsorok közötti függőleges térköz szabályozásához. Nyugodtan használhatja ezt a funkciót a szöveg megjelenésének személyre szabásához a dokumentumokban.

### GYIK

#### K: Hogyan módosíthatom egy Word-dokumentumban az adott szöveg sorközét?

V: Az Aspose.Words segítségével egyszerűen módosíthatja a Word-dokumentumban szereplő szövegek sorközét. Az API segítségével válassza ki a kívánt szöveget, és állítsa be a sorok közötti távolságot a megfelelő érték megadásával.

#### K: Lehetséges pontos térközt alkalmazni a sorok között egy Word dokumentumban?

V: Igen, az Aspose.Words lehetővé teszi, hogy pontos térközt alkalmazzon a sorok között egy Word-dokumentumban. Az API segítségével pontos értéket adhat meg a sorközhöz.

#### K: Hogyan állíthatom be a sorközt a teljes Word dokumentumban?

V: Az Aspose.Words segítségével egyszerűen beállíthatja a sorközt a teljes Word-dokumentumban. Az API által biztosított módszerekkel adja meg a kívánt sorközt a teljes dokumentumhoz.

#### K: Az Aspose.Words támogatja a többszörös sortávolságot?

V: Igen, az Aspose.Words támogatja a többszörös sortávolságot a Word dokumentumokban. Több szóközt is beállíthat, például a normál térköz 1,5-szeresét vagy kétszeresét a szöveg soraihoz.

#### K: Hogyan kerülhetem el a sorátfedéssel kapcsolatos problémákat a sorköz beállításakor?

V: A sorok közötti átfedési problémák elkerülése érdekében a sorok közötti térköz beállításakor ügyeljen a megfelelő térköz értékek kiválasztására. Tesztelje a dokumentum végső megjelenítését is, hogy megbizonyosodjon arról, hogy a szöveg olvasható és jól formázott marad.