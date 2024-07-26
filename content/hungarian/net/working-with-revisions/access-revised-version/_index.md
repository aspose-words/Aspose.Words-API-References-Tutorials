---
title: Hozzáférés a módosított verzióhoz
linktitle: Hozzáférés a módosított verzióhoz
second_title: Aspose.Words Document Processing API
description: Az Aspose.Words for .NET segítségével elérheti egy Word-dokumentum átdolgozott verzióját.
type: docs
weight: 10
url: /hu/net/working-with-revisions/access-revised-version/
---

Ebben a lépésenkénti útmutatóban bemutatjuk, hogyan érheti el a Word-dokumentum felülvizsgált verzióját az Aspose.Words for .NET használatával. Megadjuk Önnek a teljes forráskódot, és megmutatjuk, hogyan kell formázni a markdown kimenetet.

## 1. lépés: A dokumentum betöltése

Az első lépés a revíziókat tartalmazó dokumentum feltöltése.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## 2. lépés: Nyissa meg a felülvizsgált verziót

Most áttérünk a dokumentum átdolgozott változatára.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## 3. lépés: Böngésszen a változatok között

Ezután végigfutjuk a dokumentumban található változatokat, és konkrét információkat jelenítünk meg azokról a bekezdésekről, amelyek listaelemek.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Példa az Access Revised Version forráskódjához az Aspose.Words for .NET használatával

Íme a teljes forráskód egy dokumentum átdolgozott verziójának eléréséhez az Aspose.Words for .NET használatával:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Váltson át a dokumentum felülvizsgált verziójára.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan lehet elérni egy Word-dokumentum átdolgozott verzióját az Aspose.Words for .NET használatával. A dokumentum betöltésével, a javított verzióra navigálással és a revíziók böngészésével konkrét információkat kaphattunk a listaelemeknek minősülő bekezdésekről. Az Aspose.Words for .NET hatékony szolgáltatásokat kínál a Word-dokumentumok kezeléséhez, beleértve a véleményekhez való hozzáférést. Ezt a tudást most felhasználhatja saját Word-dokumentumai átdolgozott verziójához az Aspose.Words for .NET használatával.

### GYIK

#### K: Hogyan tölthetek be egy dokumentumot az Aspose.Words for .NET-be revíziókkal?

 V: Használja a`Document` osztályú Aspose.Words for .NET, hogy egy dokumentumot töltsön be egy változatokat tartalmazó fájlból. Megadhatja a teljes dokumentum elérési utat.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### K: Hogyan érhetem el egy dokumentum átdolgozott verzióját az Aspose.Words for .NET-ben?

 V: Használja a`RevisionsView` tulajdona a`Document` objektumot a dokumentum felülvizsgált verziójának eléréséhez. Beállíthatja az értékét`RevisionsView`tulajdonát`RevisionsView.Final` hogy a revíziók nélkül jelenítse meg a végleges verziót.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### K: Hogyan böngészhetek a dokumentumok változatai között az Aspose.Words for .NET-ben?

V: Használja a`foreach` ciklus a dokumentumban található változatok iterálásához. Használhatja a`Revisions` tulajdona a`Document` objektumot a dokumentum összes változatának gyűjteményéhez.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Itt dolgozza fel az egyes revíziókat
}
```

#### K: Hogyan ellenőrizhető, hogy egy bekezdés listaelem-e az Aspose.Words for .NET-ben?

 V: Használja a`IsListItem` tulajdona a`Paragraph` objektum annak ellenőrzésére, hogy egy bekezdés listaelem-e. A`IsListItem` ingatlan visszaadja`true` ha a bekezdés listaelem, ellenkező esetben visszaadja`false`.

```csharp
if (paragraph.IsListItem)
{
     // A bekezdés egy listaelem
}
else
{
     // A bekezdés nem listaelem
}
```