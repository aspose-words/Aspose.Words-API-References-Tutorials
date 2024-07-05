---
title: Szerezzen be revíziós típusú szavakat
linktitle: Szerezzen be revíziós típusú szavakat
second_title: Aspose.Words Document Processing API
description: Az Aspose.Words for .NET segítségével változatos szavakat kaphat Word-dokumentumban.
type: docs
weight: 10
url: /hu/net/working-with-revisions/get-revision-types/
---

Ebben a lépésről lépésre bemutatjuk, hogyan szerezheti be a szavak típusait egy Word-dokumentumban az Aspose.Words for .NET használatával. Megadjuk Önnek a teljes forráskódot, és megmutatjuk, hogyan kell formázni a markdown kimenetet.

## 1. lépés: A dokumentum betöltése

Az első lépés a revíziókat tartalmazó dokumentum feltöltése.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2. lépés: Lépjen végig a bekezdéseken

Ezután végigmegyünk a dokumentum bekezdésein, és ellenőrizzük az egyes bekezdésekhez kapcsolódó szóváltozatok típusait.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Példa forráskód a Revision Types lekéréséhez az Aspose.Words for .NET használatával

Íme a teljes forráskód, amellyel az Aspose.Words for .NET használatával lekérheti a revíziótípusokat egy dokumentumban:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## Következtetés

Ebben az oktatóanyagban megtudtuk, hogyan szerezheti be a szavak típusait egy Word-dokumentumban az Aspose.Words for .NET használatával. Követtük a lépéseket a dokumentum betöltéséhez, végigmegyünk a bekezdéseken, és ellenőriztük az egyes bekezdésekhez kapcsolódó szöveges ismertetők típusait. Mostantól ezt a tudást felhasználhatja saját Word-dokumentumaiban a szóelemzések elemzéséhez az Aspose.Words for .NET használatával.

### GYIK a szavak átdolgozásáról

#### K: Hogyan lehet dokumentumot feltölteni az Aspose.Words for .NET-be?

 V: Használja a`Document` osztályú Aspose.Words .NET-hez a dokumentum fájlból való betöltéséhez. Megadhatja a teljes dokumentum elérési utat.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### K: Hogyan léphetek végig a bekezdéseken egy dokumentumban az Aspose.Words for .NET programban?

 V: Használja a`Paragraphs` a dokumentumrész tulajdonsága a bekezdések gyűjteményének lekéréséhez. Ezután egy ciklus segítségével végighaladhat az egyes bekezdéseken.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Itt dolgozza fel az egyes bekezdéseket
}
```

#### K: Hogyan ellenőrizhető, hogy egy bekezdés át lett-e helyezve (törölve) az Aspose.Words for .NET-ben?

 V: Használjon bekezdést`IsMoveFromRevision`tulajdonság ellenőrzésére, hogy át lett-e helyezve (törölve).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // A bekezdés át lett helyezve (törölve)
}
```

#### K: Hogyan ellenőrizhető, hogy egy bekezdés át lett-e helyezve (beszúrva) az Aspose.Words for .NET-ben?

 V: Használjon bekezdést`IsMoveToRevision` tulajdonság ellenőrzésére, hogy áthelyezték-e (beszúrták).

```csharp
if (paragraph.IsMoveToRevision)
{
     // A bekezdés át lett helyezve (beszúrva)
}
```