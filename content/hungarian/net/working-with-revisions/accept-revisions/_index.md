---
title: Változások elfogadása
linktitle: Változások elfogadása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan fogadhat el Word-dokumentumok módosításait az Aspose.Words for .NET használatával
type: docs
weight: 10
url: /hu/net/working-with-revisions/accept-revisions/
---

Ebben az oktatóanyagban végigvezetjük a Word-dokumentumok módosításainak elfogadásán az Aspose.Words for .NET Verziók elfogadása funkciójával. Kövesse az alábbi lépéseket a forráskód megértéséhez és a dokumentum módosításainak elfogadásához.

## 1. lépés: Dokumentumtartalom hozzáadása és szerkesztése

Ebben a példában egy dokumentumot hozunk létre, és tartalmat adunk hozzá. Számos bekezdést használunk a változtatások és átdolgozások szemléltetésére. Itt van, hogyan:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Adjon hozzá szöveget az első bekezdéshez, majd adjon hozzá még két bekezdést.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## 2. lépés: Kövesse nyomon az értékeléseket és adjon hozzá véleményeket

Engedélyezzük a revíziókövetést, és hozzáadunk egy változatot a dokumentumhoz. Itt van, hogyan:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Ez a bekezdés egy változat, és a megfelelő „IsInsertRevision” jelzője be van állítva.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## 3. lépés: Töröljön egy bekezdést és kezelje a revíziókat

Törölünk egy bekezdést, és ellenőrizzük a mentett változatokat. Itt van, hogyan:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Miközben a revíziókat nyomon követjük, a bekezdés továbbra is létezik a dokumentumban, és az "IsDeleteRevision" jelző lesz beállítva
// és véleményként jelenik meg a Microsoft Wordben, mindaddig, amíg el nem fogadunk vagy el nem utasítunk minden véleményt.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## 4. lépés: Fogadja el a változtatásokat

A dokumentum minden módosítását elfogadjuk. Itt van, hogyan:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## 5. lépés: Állítsa le a vélemények követését

Leállítjuk a revíziók követését, hogy a dokumentum módosításai többé ne jelenjenek meg revízióként. Itt van, hogyan:

```csharp
doc.StopTrackRevisions();
```
## 6. lépés: A dokumentum mentése

 A szövegbeviteli űrlapmező beszúrása után mentse a dokumentumot a kívánt helyre a gombbal`Save`módszer. Ügyeljen arra, hogy megadja a megfelelő fájl elérési utat:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Példa forráskódra az Aspose.Words for .NET-hez használható változatok elfogadásához

Íme a teljes forráskód a dokumentum módosításainak elfogadásához az Aspose.Words for .NET használatával:


```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Adjon hozzá szöveget az első bekezdéshez, majd adjon hozzá még két bekezdést.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//Három paragrafusunk van, amelyek közül egyiket sem vették nyilvántartásba bármilyen típusú revízióként
// Ha a revíziók nyomon követése közben bármilyen tartalmat hozzáadunk/eltávolítunk a dokumentumból,
// ilyen formában jelennek meg a dokumentumban, és elfogadhatók/elutasíthatók.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Ez a bekezdés egy átdolgozás, és a megfelelő "IsInsertRevision" jelző lesz beállítva.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Szerezze be a dokumentum bekezdésgyűjteményét, és távolítsa el a bekezdést.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Mivel a revíziókat nyomon követjük, a bekezdés továbbra is létezik a dokumentumban, és az "IsDeleteRevision" lesz beállítva
// és változatként jelenik meg a Microsoft Wordben, amíg el nem fogadjuk vagy el nem utasítjuk az összes revíziót.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// A revízió törlése bekezdés eltávolításra kerül, ha elfogadjuk a változtatásokat.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// A revíziók követésének leállításával ez a szöveg normál szövegként jelenik meg.
// A revíziókat a rendszer nem veszi figyelembe a dokumentum megváltoztatásakor.
doc.StopTrackRevisions();

// Mentse el a dokumentumot.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan fogadhatunk el revíziókat egy Word-dokumentumban az Aspose.Words for .NET Verziók elfogadása funkciójával. Követtük a dokumentumok tartalmának hozzáadásához és szerkesztéséhez, a módosítások nyomon követéséhez, a módosított bekezdés törléséhez, az összes módosítás elfogadásához és a módosítások követésének leállításához szükséges lépéseket. Mostantól ezt a tudást alkalmazhatja saját Word-dokumentumai revízióinak hatékony kezelésére az Aspose.Words for .NET segítségével.

### GYIK

#### K: Hogyan engedélyezhetem a revíziókövetést az Aspose.Words for .NET-ben?

#### 1. megoldás:

 V: A revíziókövetés engedélyezéséhez az Aspose.Words for .NET-ben használja a`StartTrackRevisions` módszere a`Document` objektumot, és adja meg a szerző nevét és a revíziókövetés kezdő dátumát.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### 2. megoldás:

 V: A revíziókövetést a következővel is engedélyezheti`Document` kivitelező, amely elfogadja`trackRevisions`és`author` paramétereket.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### K: Hogyan fogadható el az összes módosítás egy dokumentumban az Aspose.Words for .NET segítségével?

 V: Használja a`AcceptAllRevisions` módszere a`Document` tiltakozik a dokumentumon végzett összes módosítás elfogadására.

```csharp
doc.AcceptAllRevisions();
```

#### K: Hogyan menthetek el egy módosított dokumentumot elfogadott változatokkal?

 Használja a`Save` módszere a`Document` objektumot a módosított dokumentum mentéséhez az elfogadott változatokkal. Ügyeljen arra, hogy a megfelelő fájl elérési utat adja meg.

```csharp
doc.Save("path/to/the/document.docx");
```

#### K: Hogyan állíthatom le az Aspose.Words for .NET változatainak követését?

 V: Használja a`StopTrackRevisions` módszere a`Document` objektumot a követési változatok leállításához.

```csharp
doc.StopTrackRevisions();
```

#### K: Hogyan törölhetek átdolgozott bekezdést egy dokumentumból az Aspose.Words for .NET segítségével?

 V: A dokumentum módosított bekezdésének eltávolításához használja a`Remove` a bekezdésgyűjtés módszere.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```