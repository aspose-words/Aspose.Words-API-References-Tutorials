---
title: Horgony megjegyzés
linktitle: Horgony megjegyzés
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan rögzítheti a megjegyzésekre adott válaszokat Word-dokumentumokban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/working-with-comments/anchor-comment/
---

Ebből az átfogó oktatóanyagból megtudhatja, hogyan rögzítheti a megjegyzésekre adott válaszokat egy Word-dokumentumban az Aspose.Words for .NET segítségével. Végigvezetjük a folyamaton, és biztosítjuk a szükséges C# kódrészleteket. Ennek az útmutatónak a végére képes lesz megjegyzéseket társítani a dokumentumokban szereplő konkrét szövegekhez.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Az Aspose.Words for .NET könyvtár telepítve van a rendszerére.

## 1. lépés: Hozzon létre egy új dokumentumot és adjon hozzá szöveget
Kezdésként hozzon létre egy új dokumentumot a Dokumentum osztály segítségével, és adja hozzá a kívánt szöveget:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## 2. lépés: Hozzon létre egy megjegyzést és adjon hozzá megjegyzéstartományt
Ezután hozzon létre egy megjegyzést, és társítsa azt egy adott szöveghez a CommentRangeStart és CommentRangeEnd objektumok segítségével:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## 3. lépés: Mentse el a dokumentumot
Miután rögzítette a megjegyzést egy adott szöveghez, mentse a dokumentumot fájlba a Dokumentum osztály Mentés metódusával:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Példa forráskód a horgony megjegyzéshez az Aspose.Words for .NET használatával
Íme a teljes forráskód a megjegyzésre adott válasz rögzítéséhez az Aspose.Words for .NET használatával:

```csharp
// Hozzon létre egy példányt a dokumentumból.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Hozzon létre három Run objektumot.
//Az első kettő szöveget, míg a harmadik egy megjegyzést futtat

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// Mindegyik Run objektumhoz tartozik egy CommentRangeStart és CommentRangeEnd objektum.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### GYIK

#### K: Mi az a megjegyzéshorgony az Aspose.Words for .NET-ben?

V: Az Aspose.Words for .NET-ben a megjegyzéshorgony egy jelölő, amely egy megjegyzést a dokumentum egy adott helyéhez kapcsol.

#### K: Hogyan adhatok hozzá megjegyzés horgonyt egy Aspose.Words for .NET dokumentumhoz?

V: Megjegyzés horgony hozzáadásához egy Aspose.Words for .NET dokumentumhoz, kövesse az oktatóanyagban említett lépéseket.

#### K: Hogyan férhetek hozzá egy meglévő megjegyzéshorgonyhoz az Aspose.Words for .NET-ben?

 V: Az Aspose.Words for .NET-ben meglévő megjegyzéshorgonyhoz hozzáférhet a`Comment.Anchor` ingatlan.

#### K: Biztosíthatok megjegyzésrögzítést az Aspose.Words for .NET-ben?

 V: Igen, eltávolíthat egy megjegyzés horgonyt az Aspose.Words for .NET-ből a`Comment.Remove` módszer.

#### K: Hogyan szerkeszthetem az Aspose.Words for .NET-ben egy megjegyzés horgonyhoz kapcsolódó megjegyzés szövegét?

V: Az Aspose.Words for .NET-ben egy megjegyzés horgonyhoz kötött megjegyzés szövegének módosításához elérheti a`Comment.Text` a megfelelő tulajdonsága`Comment` objektumot, és szükség szerint módosítsa a szöveget.

