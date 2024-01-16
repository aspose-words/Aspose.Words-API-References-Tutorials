---
title: Jelölje be a DrawingML szövegeffektust
linktitle: Jelölje be a DrawingML szövegeffektust
second_title: Aspose.Words Document Processing API
description: Ebből az oktatóanyagból megtudhatja, hogyan ellenőrizheti a DrawingML szövegeffektusokat Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fonts/check-drawingml-text-effect/
---

Ebben az oktatóanyagban végigvezetjük, hogyan ellenőrizheti a DrawingML szövegeffektusokat egy Word-dokumentumban az Aspose.Words Library for .NET segítségével. A DrawingML szövegeffektusok ellenőrzése lehetővé teszi annak meghatározását, hogy adott effektust alkalmaznak-e a szöveg egy részére. Lépésről lépésre segítünk megérteni és megvalósítani a kódot a .NET-projektben.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
- C# programozási nyelv gyakorlati ismerete
- A projektben telepített .NET Aspose.Words könyvtár
- DrawingML szövegeffektusokat tartalmazó Word dokumentum

## 1. lépés: Határozza meg a dokumentumkönyvtárat
 Először is be kell állítania a könyvtár elérési útját a Word-dokumentum helyére. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a kódban a megfelelő elérési úttal.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Töltse be a dokumentumot, és ellenőrizze a szövegeffektusokat
Ezután betöltjük a Word dokumentumot, és elérjük a futások (karaktersorozatok) gyűjteményét a dokumentum törzsének első bekezdésében. Ezután ellenőrizzük, hogy az első futás betűtípusára alkalmaztak-e konkrét DrawingML szövegeffektusokat.

```csharp
// Töltse be a dokumentumot
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Ellenőrizze a DrawingML szövegeffektusokat
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Minta forráskód a DMLText Effect ellenőrzéséhez az Aspose.Words for .NET használatával 

```csharp

// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Egy futtatás több Dml-szövegeffektust is alkalmazhat.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Következtetés
Ebben az oktatóanyagban láthattuk, hogyan ellenőrizheti a DrawingML szövegeffektusokat egy Word-dokumentumban az Aspose.Words for .NET használatával. A DrawingML szövegeffektusok ellenőrzése lehetővé teszi, hogy azonosítsa a szöveg azon részeit, amelyekre meghatározott hatások vonatkoznak. Nyugodtan használhatja ezt a funkciót a Word-dokumentumok szövegeffektusainak manipulálására és elemzésére.

### GYIK

#### K: Hogyan érhetem el a DrawingML szövegeffektusokat egy Word-dokumentumban az Aspose.Words használatával?

V: Az Aspose.Words segítségével elérheti a DrawingML szövegeffektusokat egy Word-dokumentumban a mellékelt API használatával. Böngészhet a szövegelemek között, és ellenőrizheti a szövegeffektusok meghatározott tulajdonságait, például színt, méretet stb.

#### K: Milyen típusú DrawingML szövegeffektusokat használnak általában a Word dokumentumokban?

V: A Word dokumentumokban gyakran használt DrawingML szövegeffektusok közé tartoznak az árnyékok, tükröződések, fények, színátmenetek stb. Ezek a hatások a szöveg megjelenésének és formázásának javítására használhatók.

#### K: Hogyan ellenőrizhetem a DrawingML szövegeffektusok színét egy Word dokumentumban?

V: A DrawingML szövegeffektusok színének ellenőrzéséhez egy Word-dokumentumban az Aspose.Words által biztosított módszerekkel érheti el a szövegeffektus színtulajdonságait. Így megkaphatja az adott szövegeffektushoz használt színt.

#### K: Lehetséges a szövegeffektusok ellenőrzése több szakaszt tartalmazó Word dokumentumokban?

V: Igen, az Aspose.Words lehetővé teszi a szövegeffektusok ellenőrzését a több szakaszt tartalmazó Word dokumentumokban. A dokumentum egyes szakaszai között navigálhat, és az egyes szakaszokhoz külön-külön hozzáférhet a szövegeffektusokhoz.

#### K: Hogyan ellenőrizhetem a DrawingML szövegeffektus átlátszatlanságát egy Word dokumentumban?

V: A DrawingML szövegeffektusok átlátszatlanságának ellenőrzéséhez egy Word-dokumentumban az Aspose.Words által biztosított módszerekkel érheti el a szövegeffektus átlátszatlansági tulajdonságait. Ez lehetővé teszi az átlátszatlanság értékének alkalmazását az adott szövegeffektusra.