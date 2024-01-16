---
title: Beágyazott mezők beszúrása
linktitle: Beágyazott mezők beszúrása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be egyszerűen beágyazott mezőket Word-dokumentumaiba az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fields/insert-nested-fields/
---

Az alábbiakban egy lépésről lépésre bemutatjuk a C# forráskódot, amely az Aspose.Words for .NET „Beágyazott mezők beszúrása” funkcióját használja. A kívánt eredmény elérése érdekében gondosan kövesse az egyes lépéseket.

## 1. lépés: Dokumentumkönyvtár beállítása

A megadott kódban meg kell adnia dokumentumai könyvtárát. Cserélje le a „DOKUMENTUMKÖNYVTÁR” értéket a dokumentumkönyvtár megfelelő elérési útjára.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: A Document és a DocumentBuilder létrehozása

Kezdjük egy új dokumentum létrehozásával és a DocumentBuilder inicializálásával.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Oldaltörések beszúrása

Egy hurkot használunk több oldaltörés beszúrására a dokumentumba.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## 4. lépés: Lépjen a láblécre

 Használjuk a`MoveToHeaderFooter()` a DocumentBuilder metódusával a kurzort a fő láblécre mozgatja.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## 5. lépés: A beágyazott mező beszúrása

 A DocumentBuildert használjuk`InsertField()`módszer beágyazott mező beszúrására a láblécbe.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 Végül hívjuk a`Update()` módszer a mező frissítéséhez.

```csharp
field. Update();
```

### Minta forráskód beágyazott mezők beszúrásához az Aspose.Words for .NET segítségével

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozza létre a dokumentumot és a DocumentBuildert.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Oldaltörések beszúrása.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// Ugrás a láblécre.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Beágyazott mező beszúrása.
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// Frissítse a mezőt.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

Ebben a példában új dokumentumot hoztunk létre, oldaltöréseket szúrtunk be, a kurzort a láblécbe mozgattuk, majd beszúrtunk egy beágyazott mezőt a láblécbe.

### GYIK

#### K: Hogyan illeszthetek be beágyazott mezőket egy Word dokumentumba az Aspose.Words for .NET használatával?

V: Ha beágyazott mezőket szeretne beszúrni egy Word-dokumentumba az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:

1. Szerezze meg azt a bekezdést, ahová be szeretné szúrni a beágyazott mezőket.
2.  Hozzon létre egy`FieldStart` objektum a szülő mezőhöz.
3.  Adja hozzá a gyermekmezőket a`FieldStart.NextSibling` módszer átadja a megfelelőt`FieldStart` objektumok paraméterként.

#### K: Milyen előnyökkel jár a beágyazott mezők használata egy Word-dokumentumban az Aspose.Words for .NET segítségével?

V: A beágyazott mezők használata számos előnnyel jár az Aspose.Words for .NET programmal készült Word-dokumentumokban. Ez nagyobb rugalmasságot tesz lehetővé a dinamikus dokumentumsablonok létrehozásában, mivel lehetővé teszi a változó értékek és számítások beillesztését a beágyazott mezőkbe. A beágyazott mezők megkönnyíthetik az automatikus tartalomgenerálást is, például tartalomjegyzékek, oldalszámok stb. létrehozását.

#### K: Lehetnek-e többszintű beágyazott mezők egy Word-dokumentumban az Aspose.Words for .NET segítségével?

 V: Igen, lehetségesek többszintű beágyazott mezők egy Word-dokumentumban az Aspose.Words for .NET segítségével. A beágyazott mezők komplex hierarchiáját hozhatja létre a`FieldStart.NextSibling` metódus gyermekmezők hozzáadásához a meglévő szülőmezőkhöz.

#### K: Hogyan szabhatom testre a beágyazott mezők tulajdonságait egy Word-dokumentumban az Aspose.Words for .NET segítségével?

 V: A Word-dokumentumban lévő beágyazott mezők tulajdonságainak testreszabásához az Aspose.Words for .NET segítségével elérheti a megfelelő`FieldStart`objektumokat, és szükség szerint módosítsa tulajdonságaikat. A kívánt eredmény elérése érdekében beállíthatja a beágyazott mezők formázási beállításait, értékeit, számításait stb.

#### K: Beágyazott mezők beszúrása befolyásolja a Word-dokumentum teljesítményét az Aspose.Words for .NET használatával?

V: A beágyazott mezők beszúrása befolyásolhatja a Word-dokumentum teljesítményét az Aspose.Words for .NET használatával, különösen akkor, ha a dokumentum nagyszámú beágyazott mezőt vagy összetett hierarchiát tartalmaz. Javasoljuk, hogy optimalizálja a kódot, elkerülve a szükségtelen vagy ismételt műveleteket a beágyazott mezőkön a teljesítmény javítása érdekében.