---
title: Csomópont mozgatása nyomon követett dokumentumban
linktitle: Csomópont mozgatása nyomon követett dokumentumban
second_title: Aspose.Words Document Processing API
description: Csomópontok mozgatása nyomon követett dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-revisions/move-node-in-tracked-document/
---

Ebben a részletes útmutatóban végigvezetjük, hogyan helyezhet át egy csomópontot egy nyomon követett Word-dokumentumban az Aspose.Words for .NET használatával. Megadjuk Önnek a teljes forráskódot, és megmutatjuk, hogyan kell formázni a markdown kimenetet.

## 1. lépés: A dokumentum létrehozása

Az első lépés egy új dokumentum létrehozása és bekezdések hozzáadása.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## 2. lépés: Kövesse nyomon a változatokat

Engedélyezni fogjuk a revíziókövetést a dokumentumban.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## 3. lépés: Helyezzen át egy csomópontot

A revíziók generálása közben áthelyezünk egy csomópontot (bekezdést) egyik pozícióból a másikba.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## 4. lépés: Állítsa le a vélemények követését

Leállítjuk a revíziók követését a dokumentumban.

```csharp
doc.StopTrackRevisions();
```

## 5. lépés: A dokumentum mentése

 A szövegbeviteli űrlapmező beszúrása után mentse a dokumentumot a kívánt helyre a gombbal`Save`módszer. Ügyeljen arra, hogy megadja a megfelelő fájl elérési utat:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Példa a Move Node In Tracked Document forráskódjához az Aspose.Words for .NET használatával

Itt található a teljes forráskód egy nyomon követett dokumentumban lévő csomópont mozgatásához az Aspose.Words for .NET használatával:


```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Kezdje el a revíziók követését.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Verziókat generál, amikor egy csomópontot egyik helyről a másikra helyez át.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Állítsa le a revíziók követésének folyamatát.
doc.StopTrackRevisions();

// 3 további bekezdés található az áthelyezési tartományban.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan helyezhet át egy csomópontot egy nyomon követett Word-dokumentumban az Aspose.Words for .NET használatával. A dokumentum létrehozásának, a revíziókövetés engedélyezésének, a csomópont áthelyezésének és a revíziókövetés leállításának lépéseit követve sikeresen végrehajtottuk ezt a manipulációt. Az Aspose.Words for .NET egy hatékony eszköz Word-dokumentumokkal történő szövegfeldolgozáshoz, és fejlett szolgáltatásokat kínál a revíziók kezeléséhez. Mostantól ezt a tudást használhatja csomópontok áthelyezésére saját Word-dokumentumaiban, miközben az Aspose.Words for .NET használatával nyomon követheti a revíziókat.

### GYIK

#### K: Hogyan engedélyezhetem a revíziókövetést egy Aspose.Words for .NET dokumentumban?

 V: Ha engedélyezni szeretné a revíziókövetést egy Aspose.Words for .NET dokumentumban, használja a`StartTrackRevisions` módszere a`Document` tárgy. Ez a módszer a revíziók szerzőjének nevét és a revíziók nyomon követésének kezdő dátumát veszi paraméterként.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### K: Hogyan helyezhetek át egy csomópontot egy nyomon követett dokumentumban revíziók generálása nélkül?

 V: Ha egy nyomon követett dokumentumban szeretne áthelyezni egy csomópontot revíziók generálása nélkül, használhatja a`Remove`és`InsertAfter` vagy`InsertBefore` módszerei a`Node` tárgy. Például egy bekezdés másik bekezdés utáni áthelyezéséhez a következő kódot használhatja:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### K: Hogyan állíthatom le a revíziókövetést egy Aspose.Words for .NET dokumentumban?

 V: Az Aspose.Words for .NET dokumentumban a revíziók követésének leállításához használja a`StopTrackRevisions` módszere a`Document` tárgy.

```csharp
doc.StopTrackRevisions();
```