---
title: Állítsa be a lábjegyzet és a végjegyzet pozícióját
linktitle: Állítsa be a lábjegyzet és a végjegyzet pozícióját
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthatja be a lábjegyzetek és végjegyzetek pozícióját a Word dokumentumokban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

Ebben a lépésenkénti oktatóanyagban bemutatjuk, hogyan használhatja az Aspose.Words for .NET-et a lábjegyzetek és végjegyzetek pozíciójának beállításához egy Word-dokumentumban. Elmagyarázzuk a mellékelt C# forráskódot, és megmutatjuk, hogyan implementálhatja azt saját projektjeibe.

 A kezdéshez győződjön meg arról, hogy az Aspose.Words for .NET telepítve van és be van állítva a fejlesztői környezetben. Ha még nem tette meg, töltse le és telepítse a könyvtárat innen[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1. lépés: A dokumentumobjektum inicializálása

 Először inicializálja a`Document` objektumot a forrásdokumentum elérési útjának megadásával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## 2. lépés: A lábjegyzet és a végjegyzet pozíciójának beállítása

 Ezután nyissa meg a`FootnoteOptions` és`EndnoteOptions` a dokumentum tulajdonságait a lábjegyzetek és végjegyzetek pozíciójának beállításához. Ebben a példában a lábjegyzetek helyét a szöveg alatt, a végjegyzeteket pedig a szakasz végén állítjuk be:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## 3. lépés: A dokumentum mentése

Végül mentse el a módosított dokumentumot:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Ez az! Sikeresen beállította a lábjegyzetek és végjegyzetek pozícióját egy Word-dokumentumban az Aspose.Words for .NET segítségével.

### Példa forráskód a Set Footnote and Endnote Position funkcióhoz az Aspose.Words for .NET használatával

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Nyugodtan használja ezt a kódot saját projektjeiben, és módosítsa saját igényei szerint.

### GYIK

#### K: Hogyan helyezhetem el a lábjegyzeteket és a végjegyzeteket az Aspose.Words-ben?

 V: A lábjegyzetek és végjegyzetek elhelyezéséhez az Aspose.Words-ben a`FootnoteOptions` osztály és a`Position` ingatlan. Ezt a tulajdonságot bármilyen értékre beállíthatja, mint pl`BottomOfPage` (a lap alján) ill`EndOfSection` (a rész végén).

#### K: Testreszabható a lábjegyzetek és végjegyzetek pozíciója a dokumentum egyes oldalaihoz vagy szakaszaihoz?

V: Igen, személyre szabható a lábjegyzetek és végjegyzetek pozíciója a dokumentum egyes oldalaihoz vagy szakaszaihoz. Használhatja az Aspose.Words szakasz- és oldalkezelési módszereket a lábjegyzetek és végjegyzetek konkrét pozícióinak meghatározásához.

#### K: Hogyan távolíthatok el lábjegyzeteket vagy végjegyzeteket egy dokumentumból?

 V: Az Aspose.Words dokumentumból lábjegyzetek vagy végjegyzetek eltávolításához megfelelő módszereket használhat, mint pl.`RemoveAllFootnotes` az összes lábjegyzet eltávolításához ill`RemoveAllEndnotes` az összes végjegyzet eltávolításához. E műveletek végrehajtása után mindenképpen mentse el a dokumentumot.

#### K: Elhelyezhetők a lábjegyzetek és a végjegyzetek az oldalmargókon kívül?

Nem, alapértelmezés szerint a lábjegyzetek és végjegyzetek nem helyezhetők el az Aspose.Words oldalmargóin kívül. Szükség esetén azonban módosíthatja a dokumentum margóit, hogy több hely maradjon a lábjegyzetek és a végjegyzetek számára.

#### K: Testreszabhatók a lábjegyzetek és a végjegyzetek meghatározott betűtípusokkal vagy formázási stílusokkal?

V: Igen, az Aspose.Words-ben testreszabhatja a lábjegyzeteket és a végjegyzeteket meghatározott betűtípusokkal vagy formázási stílusokkal. A rendelkezésre álló módszereket és tulajdonságokat használhatja betűstílusok, színek, betűméretek stb. lábjegyzetek és végjegyzetek alkalmazására.