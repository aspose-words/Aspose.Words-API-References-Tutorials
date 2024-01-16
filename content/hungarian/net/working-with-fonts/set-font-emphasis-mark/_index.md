---
title: Állítsa be a Font Emphasis Mark
linktitle: Állítsa be a Font Emphasis Mark
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthatja be a betűk kiemelésének stílusát egy Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/working-with-fonts/set-font-emphasis-mark/
---

Ebben az oktatóanyagban bemutatjuk, hogyan állíthatja be a betűtípus-kiemelés stílusát egy Word-dokumentumban az Aspose.Words for .NET használatával. A betűk kiemelése bizonyos szavak vagy kifejezések kiemelésére szolgál a szövegben.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
- C# programozási nyelv gyakorlati ismerete
- A projektben telepített .NET Aspose.Words könyvtár

## 1. lépés: Határozza meg a dokumentumkönyvtárat
 Először állítsa be a könyvtár elérési útját a Word-dokumentum helyére. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a kódban a megfelelő elérési úttal.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: A dokumentum létrehozása és testreszabása
 Hozzon létre egy példányt a`Document` osztály és egy kapcsolódó`DocumentBuilder` a dokumentumtartalom felépítéséhez. Használja a`Font.EmphasisMark` tulajdonság a betűk kiemelési stílusának beállításához`EmphasisMark.UnderSolidCircle` . Ezután használja a`Write` és`Writeln` módszerei a`DocumentBuilder` szöveg hozzáadásához a megadott betűtípussal.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## 3. lépés: Mentse el a dokumentumot
 Mentse el a dokumentumot a`Save` módszere a`Document` a megfelelő elérési úttal és fájlnévvel.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Minta forráskód a Set Font Emphasis Mark funkcióhoz az Aspose.Words for .NET használatával 

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanulta, hogyan állíthatja be a betűk kiemelési stílusát egy Word-dokumentumban az Aspose.Words for .NET használatával. Kísérletezzen a különböző hangsúlyozási stílusokkal, és használja ezt a funkciót a szavak vagy kifejezések kiemelésére a dokumentumokban.

### GYIK

#### K: Hogyan adhatok ékezetes jeleket egy adott betűtípushoz egy Word-dokumentumban az Aspose.Words használatával?

V: Ha egy Word-dokumentumban az Aspose.Words használatával szeretne ékezetjeleket hozzáadni egy adott betűtípushoz, az API segítségével navigálhat a kívánt betűtípushoz, és alkalmazhatja a megfelelő ékezetes jeleket. Ez ékezetes jeleket ad a szöveghez a kiválasztott betűtípussal.

#### K: Megváltoztatható az Aspose.Words segítségével az ékezetes jelek stílusa egy Word-dokumentumban?

V: Igen, az Aspose.Words segítségével megváltoztathatja az ékezetes jelek stílusát a Word dokumentumokban. Az API lehetővé teszi a stílustulajdonságok, például a szín, a méret, a vonaltípus stb. beállítását az ékezetes jelek megjelenésének testreszabásához.

#### K: Hogyan távolíthatok el minden ékezetes jelet egy Word-dokumentumból az Aspose.Words használatával?

V: Ha az Aspose.Words használatával eltávolíthat minden ékezetjelet egy Word-dokumentumból, az API segítségével böngészhet a dokumentumban, észlelheti a meglévő ékezetes jeleket, és eltávolíthatja azokat a megfelelő módszerekkel. Ezzel eltávolítja az összes kiemelő jelet a dokumentumból.

#### K: Hozzáadhatok ékezetes jeleket egy adott szövegrészhez egy Word-dokumentumban?

V: Igen, az Aspose.Words használatával ékezetes jeleket adhat a Word-dokumentum egy adott szövegrészéhez. Az API segítségével kiválaszthatja a kívánt szövegtartományt, és megfelelő kiemelő jeleket adhat hozzá a szöveg adott részéhez.

#### K: Az ékezetes jelek testreszabhatók az igényeim szerint?

V: Igen, az Aspose.Words segítségével az ékezetes jelek az Ön igényei szerint testreszabhatók. Beállíthatja az ékezetes jelek stílustulajdonságait, mint például a szín, a méret, a vonaltípus és egyebek, hogy megfeleljenek a formázási preferenciáknak.