---
title: Megjegyzés megoldva és válaszok
linktitle: Megjegyzés megoldva és válaszok
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan oldhatja fel a megjegyzéseket és a rájuk adott válaszokat a Word-dokumentumokban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/working-with-comments/comment-resolved-and-replies/
---

Ebből az átfogó oktatóanyagból megtudhatja, hogyan oldhatja meg a megjegyzéseket és a rájuk adott válaszokat egy Word-dokumentumban az Aspose.Words for .NET használatával. Végigvezetjük a folyamaton, és biztosítjuk a szükséges C# kódrészleteket. Ennek az útmutatónak a végére kezelheti a megjegyzések felbontását, valamint frissítheti a megjegyzések állapotát és a rájuk adott válaszokat.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Az Aspose.Words for .NET könyvtár telepítve van a rendszerére.

## 1. lépés: Töltse be a dokumentumot és a megjegyzéseket
Kezdésként töltse be a megjegyzéseket tartalmazó dokumentumot a Dokumentum osztály segítségével, és nyissa meg a megjegyzésgyűjteményt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## 2. lépés: A megjegyzések és válaszaik megoldása
Ezután ismételje meg a megjegyzéseket és válaszaikat, hogy megoldottként jelölje meg őket:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

fenti kódban elérjük a szülő megjegyzést, és a válaszokon keresztül iterálunk. Lekérhetjük a szülő megjegyzés azonosítóját és annak felbontási állapotát. Ezután minden megjegyzésre adott válasznál frissítjük a „Kész” jelölést, jelezve a megoldást.

## 3. lépés: Mentse el a dokumentumot
A megjegyzések feloldása és állapotfrissítése után mentse a módosított dokumentumot fájlba a Dokumentum osztály Mentés metódusával:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Példa forráskód megjegyzések és válaszaik feloldásához az Aspose.Words for .NET használatával
Íme a teljes forráskód a megjegyzések és a rájuk adott válaszok megoldásához az Aspose.Words for .NET használatával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
Ne felejtse el módosítani a kódot saját igényei szerint, beleértve a dokumentumfájl elérési útját és a további testreszabásokat

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan lehet feloldani a megjegyzéseket és a rájuk adott válaszokat egy Word-dokumentumban az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód használatával mostantól kezelheti a megjegyzések felbontását, és igénye szerint frissítheti a megjegyzések és válaszaik állapotát.

A megjegyzésfeloldás segít a visszajelzések nyomon követésében és kezelésében a dokumentumon belül. Kísérletezzen a különböző megjegyzésállapotokkal, és szabja testre azokat, hogy javítsa az együttműködést és a dokumentumok áttekintési folyamatait.

### GYIK

#### K: Hogyan oldhatok meg egy megjegyzést az Aspose.Words for .NET-ben?

 V: Az Aspose.Words for .NET-ben található megjegyzések megoldásához használhatja a`Comment.Resolve` módszer, amely meghatározza a`Comment` feloldani kívánt objektumot. Ezzel megoldottként jelöli meg a megjegyzést, és elrejti a végleges dokumentumban.

#### K: Hogyan adhatok választ egy megoldott megjegyzésre az Aspose.Words for .NET-ben?

 V: Bár a megoldott megjegyzések alapértelmezés szerint el vannak rejtve a végleges dokumentumban, továbbra is hozzáadhat választ a megoldott megjegyzésekre a`Comment.AddReply`metódus, amely megadja a válaszszöveget és azt, hogy hol szeretné hozzáadni.

#### K: Hogyan tekinthetem meg a megoldott megjegyzéseket az Aspose.Words for .NET-ben?

 V: Alapértelmezés szerint a feloldott megjegyzések el vannak rejtve a végleges dokumentumban. Megmutathatja azonban őket a`CommentOptions.ShowResolvedComments` tulajdona a`Document` objektumot és annak beállítását`true`.

#### K: Hogyan rejthetem el az összes megjegyzést, beleértve a válaszokat is, az Aspose.Words for .NET-ben?

 V: Ha az Aspose.Words for .NET-ben el szeretné rejteni az összes megjegyzést, beleértve a válaszokat is, használja a`CommentOptions.CommentDisplayMode` tulajdona a`Document` objektumot, és állítsa be`CommentDisplayMode.None`.

#### K: Szerkeszthetem egy megoldott megjegyzés szövegét az Aspose.Words for .NET-ben?

 V: Igen, szerkesztheti egy megoldott megjegyzés szövegét az Aspose.Words for .NET-ben a`Comment.Text` a megfelelő tulajdonsága`Comment` objektumot, és szükség szerint módosítani kell a szöveget.