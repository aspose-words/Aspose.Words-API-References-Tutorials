---
title: Megjegyzések hozzáadása
linktitle: Megjegyzések hozzáadása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan adhat megjegyzéseket Word-dokumentumokhoz az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/working-with-comments/add-comments/
---

Ebből az átfogó oktatóanyagból megtudhatja, hogyan fűzhet megjegyzéseket egy Word-dokumentumhoz az Aspose.Words for .NET használatával. Végigvezetjük a folyamaton, és biztosítjuk a szükséges C# kódrészleteket. Az útmutató végére megjegyzéseket illeszthet be, és személyre szabhatja azok tartalmát a dokumentumaiban.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Az Aspose.Words for .NET könyvtár telepítve van a rendszerére.

## 1. lépés: Hozzon létre egy új dokumentumot és DocumentBuildert
Kezdésként hozzon létre egy új dokumentumot a Document osztály használatával, és inicializáljon egy DocumentBuilder objektumot:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Adjon hozzá tartalmat a dokumentumhoz
Ezután adja hozzá a kívánt tartalmat a dokumentumhoz a DocumentBuilder objektum segítségével. Ebben a példában hozzáadunk néhány szöveget:

```csharp
builder.Write("Some text is added.");
```

## 3. lépés: Hozzon létre egy megjegyzést és adjon hozzá tartalmat
Megjegyzés hozzáadásához hozzon létre egy példányt a Megjegyzés osztályból, átadva a Dokumentum objektumot, a szerző nevét, a szerző kezdőbetűit és az aktuális dátumot:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Ezután fűzze hozzá a megjegyzést az aktuális bekezdéshez:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Adjon hozzá tartalmat a megjegyzéshez, például egy bekezdést és szöveget:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## 4. lépés: Mentse el a dokumentumot
A megjegyzés és annak tartalmának hozzáadása után mentse a dokumentumot fájlba a Dokumentum osztály Mentés metódusával:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Példa forráskód a megjegyzések hozzáadásához az Aspose.Words for .NET használatával
Itt található a teljes forráskód az Aspose.Words for .NET használatával történő megjegyzések hozzáadásához:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan fűzhet megjegyzéseket egy Word-dokumentumhoz az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód felhasználásával mostantól megjegyzéseket illeszthet be, és testreszabhatja azok tartalmát a dokumentumokban.

A megjegyzések hasznosak az együttműködéshez, további információk nyújtásához vagy jegyzetek készítéséhez a dokumentumon belül. Kísérletezzen különböző szerzői nevekkel, kezdőbetűkkel és megjegyzések tartalmával, hogy megfeleljen egyedi követelményeinek.

### GYIK

#### K: Hogyan fűzhetek megjegyzést egy Aspose.Words for .NET dokumentumhoz?

V: Ha megjegyzést szeretne hozzáadni egy Aspose.Words for .NET dokumentumhoz, kövesse az oktatóanyagban említett lépéseket.

#### K: Formázhatom a megjegyzés szövegét az Aspose.Words for .NET-ben?

V: Igen, az Aspose.Words for .NET-ben a megjegyzések szövegét formázhatja a rendelkezésre álló formázási tulajdonságok használatával.

#### K: Hogyan kérhetem le a dokumentumban található összes megjegyzést?

V: A dokumentumban található összes megjegyzést lekérheti a`Document.Comments` ingatlan.

#### K: Törölhetek egy adott megjegyzést az Aspose.Words for .NET-ben?

 V: Igen, eltávolíthat egy adott megjegyzést az Aspose.Words for .NET-ben a`Comment.Remove` módszer.

#### K: Hogyan módosíthatom egy meglévő megjegyzés szövegét az Aspose.Words for .NET-ben?

 V: Az Aspose.Words for .NET-ben meglévő megjegyzés szövegének módosításához elérheti a`Comment.Text` a megfelelő tulajdonsága`Comment` objektumot, és szükség szerint módosítsa a szöveget.