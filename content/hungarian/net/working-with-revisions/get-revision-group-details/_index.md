---
title: Szerezze meg a verziócsoport részleteit
linktitle: Szerezze meg a verziócsoport részleteit
second_title: Aspose.Words Document Processing API
description: Az Aspose.Words for .NET segítségével Word-dokumentumban tekintheti meg a revíziócsoport részleteit.
type: docs
weight: 10
url: /hu/net/working-with-revisions/get-revision-group-details/
---

Ebben a lépésenkénti útmutatóban bemutatjuk, hogyan szerezheti be egy Word-dokumentumban lévő változatok egy csoportjának részleteit az Aspose.Words for .NET használatával. Megadjuk Önnek a teljes forráskódot, és megmutatjuk, hogyan kell formázni a markdown kimenetet.

## 1. lépés: A dokumentum betöltése

Az első lépés a revíziókat tartalmazó dokumentum feltöltése.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2. lépés: Böngésszen a változatok között

Ezután végigfutjuk a dokumentumban található változatokat, és megjelenítjük azok részleteit, például típust, szerzőt, dátumot és átdolgozott szöveget.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Példa forráskódra a Revision Group Details lekéréséhez az Aspose.Words for .NET használatával

Íme a teljes forráskód, amellyel egy dokumentumban az Aspose.Words for .NET segítségével lekérheti a revíziók csoportjának részleteit:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan szerezheti be egy Word-dokumentumban lévő változatok egy csoportjának részleteit az Aspose.Words for .NET használatával. A ciklus és a megfelelő tulajdonságok használatával olyan részleteket tudtunk megjeleníteni, mint a revízió típusa, szerző, dátum és átdolgozott szöveg. Az Aspose.Words for .NET számos hatékony szolgáltatást kínál a Word-dokumentumok kezeléséhez, beleértve a revíziókezelést. Ezt a tudást most felhasználhatja arra, hogy a revíziócsoport részleteit saját Word-dokumentumaiba helyezze az Aspose.Words for .NET segítségével.

### GYIK

#### K: Hogyan tölthetek be egy dokumentumot az Aspose.Words for .NET-be revíziókkal?

 V: Használja a`Document` osztályú Aspose.Words for .NET, hogy egy dokumentumot töltsön be egy változatokat tartalmazó fájlból. Megadhatja a teljes dokumentum elérési utat.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### K: Hogyan szerezhetem meg az Aspose.Words for .NET-ben található revíziócsoport részleteit?

V: Menjen végig a dokumentum revízióin egy hurok segítségével, és érje el az egyes változatok tulajdonságait a kívánt részletek eléréséhez. Használhatja a`RevisionType`, `Author`, `DateTime`és`ParentNode` tulajdonságokat, hogy megkapja a revízió típusát, szerzőjét, dátumát és átdolgozott szövegét.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### K: Hogyan ellenőrizhető, hogy egy változat egy csoporthoz tartozik-e az Aspose.Words for .NET-ben?

 V: Használja a`Group` tulajdona a`Revision` objektum annak ellenőrzésére, hogy egy változat egy csoporthoz tartozik-e. Ha a`Group` ingatlan az`null`, ez azt jelenti, hogy a revízió nem tartozik egyik csoporthoz sem.

```csharp
if (revision.Group != null)
{
      // A revízió egy csoporthoz tartozik
}
else
{
      // A revízió nem tartozik egyik csoporthoz sem
}
```