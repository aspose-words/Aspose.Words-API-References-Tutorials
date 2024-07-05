---
title: Szerezze be a felülvizsgálati csoportokat
linktitle: Szerezze be a felülvizsgálati csoportokat
second_title: Aspose.Words Document Processing API
description: Szerezzen verziócsoportokat Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-revisions/get-revision-groups/
---

Ebben a lépésről lépésre bemutatjuk, hogyan töltheti le a revíziócsoportokat egy Word-dokumentumban az Aspose.Words for .NET használatával. Megadjuk Önnek a teljes forráskódot, és megmutatjuk, hogyan kell formázni a markdown kimenetet.

## 1. lépés: A dokumentum betöltése

Az első lépés a revíziókat tartalmazó dokumentum feltöltése.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2. lépés: Böngésszen a verziócsoportok között

Ezután végigfutjuk a dokumentumban található revíziócsoportokat, és megjelenítjük azok részleteit, például a szerzőt, a revíziótípust és az átdolgozott szöveget.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Példa forráskódra a Revision Groups lekéréséhez az Aspose.Words for .NET használatával

Íme a teljes forráskód, amellyel a változatcsoportokat az Aspose.Words for .NET segítségével egy dokumentumban kaphatja meg:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan töltheti le a revíziócsoportokat egy Word-dokumentumban az Aspose.Words for .NET használatával. Követtük a lépéseket a dokumentum betöltéséhez és a felülvizsgálati csoportok böngészéséhez, megjelenítve a részleteket, például a szerzőt és a vélemény típusát. Ezt a tudást most már használhatja saját Word-dokumentuma revízióinak elemzésére az Aspose.Words for .NET használatával.

### GYIK

#### K: Hogyan lehet dokumentumot feltölteni az Aspose.Words for .NET-be?

 V: Használja a`Document` osztályú Aspose.Words .NET-hez a dokumentum fájlból való betöltéséhez. Megadhatja a teljes dokumentum elérési utat.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### K: Hogyan böngészhet a revíziócsoportok között egy dokumentumban az Aspose.Words for .NET-ben?

 V: Használja a`Groups` a dokumentum tulajdonsága`Revisions`objektumot a revíziócsoportok gyűjteményének lekéréséhez. Ezután egy hurkot használhat az egyes áttekintési csoportok áttekintésére.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Itt dolgozza fel az egyes felülvizsgálati csoportokat
}
```

#### K: Hogyan lehet elérni az Aspose.Words for .NET-ben egy áttekintő csoport szerzőjét?

 V: Használja a`Author` tulajdona a`RevisionGroup` tiltakozik a revíziócsoport szerzőjének lekérésére.

```csharp
string author = group.Author;
```

#### K: Hogyan szerezhető be egy revíziócsoport revíziótípusa az Aspose.Words for .NET-ben?

 V: Használja a`RevisionType` tulajdona a`RevisionGroup` objektumot a csoport revíziótípusának lekéréséhez.

```csharp
string revisionType = group.RevisionType;
```