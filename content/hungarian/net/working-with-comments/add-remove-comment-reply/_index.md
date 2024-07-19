---
title: Hozzáadás Megjegyzés eltávolítása Válasz
linktitle: Hozzáadás Megjegyzés eltávolítása Válasz
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan adhat hozzá és távolíthat el megjegyzésekre adott válaszokat Word-dokumentumokban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/working-with-comments/add-remove-comment-reply/
---

Ebből az átfogó oktatóanyagból megtudhatja, hogyan adhat hozzá és távolíthat el megjegyzésekre adott válaszokat egy Word-dokumentumban az Aspose.Words for .NET használatával. Végigvezetjük a folyamaton, és biztosítjuk a szükséges C# kódrészleteket. Ennek az útmutatónak a végére kezelheti a megjegyzésekre adott válaszokat, és saját igényei szerint testreszabhatja azokat.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Az Aspose.Words for .NET könyvtár telepítve van a rendszerére.

## 1. lépés: Töltse be a dokumentumot
Kezdésként töltse be a megjegyzéseket tartalmazó dokumentumot a Dokumentum osztály használatával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## 2. lépés: Nyissa meg a Megjegyzések és a válaszok kezelését
Ezután nyissa meg a megjegyzést a dokumentumból a GetChild metódussal a NodeType.Comment paraméterrel:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

Válasz eltávolításához a megjegyzésből használja a RemoveReply metódust, és adja meg a kívánt válaszindexet:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

Ha új választ szeretne adni a megjegyzéshez, használja az AddReply metódust, és adja meg a szerző nevét, a szerző kezdőbetűit, a dátumot és az időt, valamint a válasz szövegét:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## 3. lépés: Mentse el a dokumentumot
A megjegyzésválaszok hozzáadása vagy eltávolítása után mentse a dokumentumot fájlba a Dokumentum osztály Mentés metódusával:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Példa forráskód a megjegyzésválaszok hozzáadásához és eltávolításához az Aspose.Words for .NET használatával
Itt található a teljes forráskód a megjegyzésekre adott válaszok hozzáadásához és eltávolításához az Aspose.Words for .NET használatával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan adhat hozzá és távolíthat el megjegyzésekre adott válaszokat egy Word-dokumentumban az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a megadott forráskód használatával mostantól kezelheti a megjegyzésekre adott válaszokat, és igényei szerint testreszabhatja azokat.

A megjegyzésekre adott válaszok lehetővé teszik az együttműködésen alapuló megbeszéléseket és visszajelzéseket a dokumentumon belül. Kísérletezzen a válaszok különböző szerzőivel, kezdőbetűivel, dátumaival és szövegeivel, hogy javítsa az együttműködést és a kommunikációt a dokumentumokon belül.

### GYIK

#### K: Hogyan adhatok hozzá megjegyzést az Aspose.Words for .NET-hez?

 V: Ha megjegyzést szeretne hozzáadni az Aspose.Words for .NET-hez, használja a`Comment.AddComment` metódus, amely megadja a megjegyzés szövegét, és azt, hogy hova kívánja hozzáadni a dokumentumban.

#### K: Hogyan távolíthatok el egy megjegyzést az Aspose.Words for .NET-ből?

V: Az Aspose.Words for .NET-ben található megjegyzés eltávolításához használja a`Comment.Remove` módszer, amely meghatározza a`Comment` az eltávolítani kívánt objektumot.

#### K: Válaszolhatok egy megjegyzésre az Aspose.Words for .NET-ben?

 V: Igen, válaszolhat egy megjegyzésre az Aspose.Words for .NET-ben a`Comment.AddReply` módszerrel, amely megadja a válaszszöveget, és azt, hogy hova szeretné hozzáadni a dokumentumban.

#### K: Hogyan érhetem el az Aspose.Words for .NET meglévő megjegyzéseit?

 V: Az Aspose.Words for .NET meglévő megjegyzéseit a következővel érheti el`CommentCollection` tulajdona a`Document` tárgy. Ez lehetővé teszi, hogy a dokumentumban található összes megjegyzés között böngésszen.

#### K: Szerkeszthetem a megjegyzés szövegét az Aspose.Words for .NET-ben?

 V: Igen, szerkesztheti egy megjegyzés szövegét az Aspose.Words for .NET-ben a`Comment.Text` a megfelelő tulajdonsága`Comment` objektumot, és szükség szerint módosítani kell a szöveget.