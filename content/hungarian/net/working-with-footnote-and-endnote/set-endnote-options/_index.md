---
title: Állítsa be a végjegyzet beállításait
linktitle: Állítsa be a végjegyzet beállításait
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthat be végjegyzetbeállításokat Word dokumentumokban az Aspose.Words for .NET használatával. Lépésről lépésre bemutató példa forráskóddal.
type: docs
weight: 10
url: /hu/net/working-with-footnote-and-endnote/set-endnote-options/
---

Ebben a lépésenkénti oktatóanyagban bemutatjuk, hogyan használhatja az Aspose.Words for .NET-et a végjegyzetbeállítások megadásához egy Word-dokumentumban. Elmagyarázzuk a mellékelt C# forráskódot, és megmutatjuk, hogyan implementálhatja azt saját projektjeibe.

 A kezdéshez győződjön meg arról, hogy az Aspose.Words for .NET telepítve van és be van állítva a fejlesztői környezetben. Ha még nem tette meg, töltse le és telepítse a könyvtárat innen[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1. lépés: A dokumentumobjektum inicializálása

 Először inicializálja a`Document` objektumot a forrásdokumentum elérési útjának megadásával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## 2. lépés: A DocumentBuilder objektum inicializálása

 Ezután inicializálja a`DocumentBuilder` objektum műveletek végrehajtásához a dokumentumon:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Szöveg és végjegyzet hozzáadása

 Használja a`Write` módszere a`DocumentBuilder` objektumot szöveg hozzáadásához a dokumentumhoz, és a`InsertFootnote` módszer a végjegyzet beszúrására:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## 4. lépés: A végjegyzet beállításainak megadása

 Hozzáférés a`EndnoteOptions` dokumentum tulajdonsága a végjegyzet beállításainak módosításához. Ebben a példában az újraindítási szabályt úgy állítjuk be, hogy minden oldalon újrainduljon, a pozíciót pedig a szakasz végén:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## 5. lépés: A dokumentum mentése

Végül mentse el a módosított dokumentumot:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Ez az! Sikeresen beállította a végjegyzetbeállításokat egy Word-dokumentumban az Aspose.Words for .NET használatával.

### Példa a Set Endnote Options for Aspose.Words for .NET forráskódjához

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Nyugodtan használja ezt a kódot saját projektjeiben, és módosítsa saját igényei szerint.

### GYIK

#### K: Hogyan formázhatom a végjegyzeteket az Aspose.Words-ben?

 V: Az Aspose.Words végjegyzeteinek stílusozásához használhatja a`EndnoteOptions` osztály és a`SeparatorNoteTextStyle` ingatlan. Ezzel a tulajdonsággal megadhatja a betűtípust, -méretet, -színt stb. a végjegyzetekhez.

#### K: Testreszabható a végjegyzetek számozása egy dokumentumban?

 V: Igen, személyre szabható a végjegyzetek számozása egy dokumentumban. Használhatja a`RestartRule`és`NumberStyle` tulajdonságai a`EndnoteOptions` osztályban meghatározott újraindítási szabályok és számozási stílusok meghatározásához.

#### K: Hogyan helyezhetem el a végjegyzeteket egy dokumentumban?

V: A végjegyzetek dokumentumban való elhelyezéséhez használhatja a`Position` tulajdona a`EndnoteOptions` osztály. Megadhatja, hogy a végjegyzetek az egyes oldalak aljára, az egyes szakaszok végére vagy a dokumentum végére kerüljenek-e.

#### K: Testreszabhatom a végjegyzet számozási formátumát?

 V: Igen, testreszabhatja a végjegyzetek számozásának formátumát az Aspose.Words-ben. Használja a`NumberFormat` tulajdona a`EndnoteOptions` osztályba a kívánt formátum beállításához, például arab számok, római számok, betűk stb.

#### K: Folytatni lehet a végjegyzetek számozását a dokumentum szakaszai között?

 V: Igen, folytatható a végjegyzetek számozása a dokumentum szakaszai között. Használja a`RestartRule` tulajdona a`EndnoteOptions` osztályba, és állítsa be`RestartContinuous` hogy a számozás folytatódjon a szakaszok között.