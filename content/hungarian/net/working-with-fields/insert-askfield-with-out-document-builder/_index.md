---
title: Az ASKField beszúrása Dokumentumkészítő nélkül
linktitle: Az ASKField beszúrása Dokumentumkészítő nélkül
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be ASK mezőt Word-dokumentumaiba az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Itt található egy lépésről lépésre bemutatott útmutató a C# forráskód leírásához, amely az Aspose.Words for .NET "ASK mező beszúrása DocumentBuilder nélkül" funkcióját használja. A kívánt eredmény elérése érdekében gondosan kövesse az egyes lépéseket.

## 1. lépés: Dokumentumkönyvtár beállítása

A megadott kódban meg kell adnia dokumentumai könyvtárát. Cserélje le a „DOKUMENTUMKÖNYVTÁR” értéket a dokumentumkönyvtár megfelelő elérési útjára.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: A dokumentum és a bekezdés létrehozása

Kezdjük egy új dokumentum létrehozásával és az első bekezdés lekérésével.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 3. lépés: Az ASK mező beszúrása

 Használjuk a`AppendField()` módszer egy ASK mező beillesztéséhez a bekezdésbe.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Ezután a kívánt értékek megadásával konfiguráljuk az ASK mező különböző tulajdonságait.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Végül hívjuk a`Update()` módszer a mező frissítéséhez.

```csharp
field. Update();
```

### Példa a forráskódra egy ASK mező beszúrásához DocumentBuilder nélkül az Aspose.Words for .NET-hez

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentumkészítés.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Írja be az ASK mezőt.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

Ebben a példában létrehoztunk egy új dokumentumot, beszúrtunk egy ASK mezőt a DocumentBuilder használata nélkül, konfiguráltuk a mező különféle tulajdonságait, és elmentettük a dokumentumot egy megadott fájlnévvel.

Ezzel véget is értünk az "Insert ASK Field Without DocumentBuilder" funkció használatáról szóló útmutatónknak az Aspose.Words for .NET-hez.

### GYIK

#### K: Mi az ASK mező az Aspose.Words-ben?

V: Az Aspose.Words ASK mezője arra szolgál, hogy egy dokumentum megnyitásakor kérdést tegyen fel a felhasználónak. Gyakran használják konkrét információk vagy visszajelzések kérésére, amelyek felhasználónként változhatnak.

#### K: Hogyan lehet beszúrni ASK mezőt Word dokumentumba anélkül, hogy a Document Buildert használnánk az Aspose.Wordsben?

V: Ha egy ASK mezőt szeretne beszúrni egy Word dokumentumba anélkül, hogy az Aspose.Words dokumentumkészítőjét használná, kövesse az alábbi lépéseket:

1. Importálja a dokumentumot és a mezőosztályt az Aspose.Words.Fields névtérből.
2. Hozzon létre egy példányt a dokumentumból a meglévő dokumentum betöltésével.
3. Használja az InsertField metódust egy ASK mező beszúrásához a kérdés nevének megadásával.
4. Mentse el a dokumentumot.

#### K: Hogyan kaphatom meg a felhasználói választ egy ASK mezőre egy Word dokumentumban?

V: Ahhoz, hogy a felhasználó választ kapjon egy Word-dokumentum ASK mezőjére, használhatja a Dokumentum osztályban elérhető GetFieldNames metódust. Ez a metódus a dokumentumban található mezők nevének listáját adja vissza. Ezután ellenőrizheti, hogy az ASK mező neve szerepel-e a listában, és lekérheti a kapcsolódó választ.

#### K: Az ASK mezővel további információkat kérhet a felhasználótól?

V: Igen, az ASK mezővel több információ kérhető a felhasználótól. Több ASK mezőt is beszúrhat a dokumentumba, mindegyikhez más-más kérdés tartozik. A dokumentum megnyitásakor a felhasználó a megfelelő válaszokat kéri.