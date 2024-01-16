---
title: Word-dokumentum felosztása oldalak szerint
linktitle: Word-dokumentum felosztása oldalak szerint
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan oszthat fel egy Word-dokumentumot egyes oldalakra az Aspose.Words for .NET használatával. Ez a hatékony API leegyszerűsíti a dokumentumok felosztásának folyamatát, így hatékony és kényelmes.
type: docs
weight: 10
url: /hu/net/split-document/page-by-page/
---

Ebben az oktatóanyagban végigvezetjük, hogyan oszthat fel egy Word-dokumentumot egyes oldalakra az Aspose.Words for .NET dokumentumfeldolgozási funkciójával. Kövesse az alábbi lépéseket, hogy megértse a forráskódot, és külön dokumentumokat kapjon minden oldalhoz.

## 1. lépés: A dokumentum betöltése

A kezdéshez adja meg a dokumentum könyvtárát, és töltse be a dokumentumot egy dokumentum objektumba. Itt van, hogyan:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## 2. lépés: Dokumentum felosztása oldalanként

Most végigfutjuk a dokumentum minden oldalát, és külön oldalakra bontjuk a dokumentumot. Itt van, hogyan:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Mentse el az egyes oldalakat külön dokumentumként.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

### Példa forráskód oldalról oldalra az Aspose.Words for .NET használatával

Íme az Aspose.Words for .NET oldalról oldalra funkciójának teljes forráskódja:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

int pageCount = doc.PageCount;

for (int page = 0; page < pageCount; page++)
{
	// Mentse el az egyes oldalakat külön dokumentumként.
	Document extractedPage = doc.ExtractPages(page, 1);
	extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
}


```

Ezzel a kóddal egy Word-dokumentumot különálló oldalakra oszthat fel az Aspose.Words for .NET használatával. Szükség esetén külön dokumentumokat is egyesíthet.

## Következtetés

Gratulálunk! Megtanulta, hogyan oszthat fel egy Word-dokumentumot egyes oldalakra az Aspose.Words for .NET oldalról oldalra funkciójával. A megadott forráskód követésével a dokumentum minden oldalát kibonthatja, és külön dokumentumként mentheti el.

A dokumentum oldalak szerinti felosztása hasznos lehet, ha meghatározott oldalakkal kell dolgoznia vagy a tartalmat részletesen kell elosztania. Az Aspose.Words for .NET hatékony API-t biztosít, amely leegyszerűsíti a dokumentumok felosztásának folyamatát, így hatékony és kényelmes.

Nyugodtan fedezze fel az Aspose.Words for .NET által kínált egyéb funkciókat a dokumentumfeldolgozási képességek javítása és a munkafolyamat egyszerűsítése érdekében.

### GYIK

#### Hogyan oszthatok fel egy dokumentumot több oldalra az Aspose.Words for .NET használatával?

 Ha egy dokumentumot több oldalra szeretne felosztani, használhatja a`ExtractPages` Az Aspose.Words API módszere az oldaltartomány lekéréséhez. A kezdőoldal és a kibontandó oldalak számának megadásával oldalanként külön dokumentumokat hozhat létre.

#### Testreszabhatom a kimeneti formátumot, amikor egy dokumentumot oldalanként osztok fel?

Igen, az Aspose.Words for .NET különféle kimeneti formátumokat támogat a dokumentumok oldalankénti felosztása során. Igényeitől függően minden oldalt külön dokumentumként menthet, például DOCX, PDF, HTML és még sok más formátumban.

#### Feloszthatok egy dokumentumot egy adott oldaltartományra?

Teljesen! Az Aspose.Words for .NET lehetővé teszi a dokumentum egy adott oldaltartományra való felosztását. A kezdőoldal és a kibontandó oldalak számának beállításával pontosan meghatározhatja a dokumentum felosztásának oldaltartományát.

#### Lehetséges a felosztott dokumentumokat egyetlen dokumentumba visszaolvasztani?

Igen, az Aspose.Words for .NET által biztosított egyesítési funkció segítségével a felosztott dokumentumokat egyetlen dokumentummá egyesítheti. A különálló dokumentumok összevonásával szükség szerint újra létrehozhatja az eredeti dokumentumot, vagy új, eltérő szerkezetű dokumentumot hozhat létre.