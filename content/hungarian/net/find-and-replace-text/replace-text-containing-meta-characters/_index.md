---
title: Meta karaktereket tartalmazó szöveg csere
linktitle: Meta karaktereket tartalmazó szöveg csere
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan cserélheti le a metakaraktereket tartalmazó szöveget Word dokumentumokban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/find-and-replace-text/replace-text-containing-meta-characters/
---
Ebben a cikkben megvizsgáljuk a fenti C# forráskódot, hogy megértsük, hogyan használható a Meta karaktereket tartalmazó Word szövegcsere funkciója az Aspose.Words for .NET könyvtárban. Ez a funkció lehetővé teszi bizonyos metakaraktereket tartalmazó dokumentum szövegrészeinek cseréjét.

## Előfeltételek

- C# nyelv alapismerete.
- .NET fejlesztői környezet telepített Aspose.Words könyvtárral.

## 1. lépés: Új dokumentum létrehozása

 Mielőtt elkezdené használni a metakarakterek szövegcseréjét, létre kell hoznunk egy új dokumentumot az Aspose.Words for .NET használatával. Ezt úgy lehet megtenni, hogy a`Document` tárgy:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2. lépés: Szúrjon be szöveget a dokumentumba

 Ha megvan a dokumentumunk, szöveget szúrhatunk be az a segítségével`DocumentBuilder` tárgy. Példánkban a`Writeln` módszer több bekezdés szövegének különböző szakaszokba történő beillesztésére:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder. Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

## 3. lépés: A keresési és cserelehetőségek konfigurálása

 Most az opciók keresését és cseréjét a a segítségével konfiguráljuk`FindReplaceOptions` tárgy. Példánkban a lecserélt bekezdések igazítását "Középre" állítottuk:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## 4. lépés: Metakaraktereket tartalmazó szöveg cseréje

 Használjuk a`Range.Replace`módszer a metakaraktereket tartalmazó szöveg cseréjének végrehajtására. Példánkban a "szakasz" szó minden előfordulását, amelyet egy bekezdéstörés követ, lecseréljük ugyanazzal a szóval, amelyet több kötőjel követ, és egy új bekezdéstörés:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## 5. lépés: Egyéni szöveges címke cseréje

 Mi is használjuk a`Range.Replace` módszer az egyéni "{insert-section}" szöveges címke szakasztöréssel. Példánkban a " "{insert-section}" és "&b"-vel szakasztörés beszúrásához:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## 6. lépés: A szerkesztett dokumentum mentése

Végül a módosított dokumentumot a megadott könyvtárba mentjük a`Save` módszer:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### Példa forráskód a metakaraktereket tartalmazó szöveg cseréjéhez az Aspose.Words for .NET használatával

Íme a teljes példaforráskód, amely bemutatja a metakaraktereket tartalmazó szövegcsere használatát Aspose.Words for .NET-hez:

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Font.Name = "Arial";
	builder.Writeln("First section");
	builder.Writeln("  1st paragraph");
	builder.Writeln("  2nd paragraph");
	builder.Writeln("{insert-section}");
	builder.Writeln("Second section");
	builder.Writeln("  1st paragraph");

	FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
	findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;

	// Kétszer minden bekezdéstörést a "szakasz" szó után, adjon hozzá egyfajta aláhúzást, és tegye középre.
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// Szakasztörés beszúrása egyéni szövegcímke helyett.
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## Következtetés

Ebben a cikkben megvizsgáltuk a C# forráskódot, hogy megértsük, hogyan használható az Aspose.Words for .NET metakaraktereket tartalmazó szöveg csere funkciója. A dokumentum létrehozásához, szöveg beszúrásához, metakaraktereket tartalmazó szöveg cseréjéhez és a módosított dokumentum mentéséhez egy lépésről lépésre szóló útmutatót követtünk.

### GYIK

#### K: Mi az Aspose.Words for .NET metakaraktereket tartalmazó szöveg cseréje funkciója?

V: A Metakaraktereket tartalmazó szöveg cseréje funkciója az Aspose.Words for .NET-ben lehetővé teszi bizonyos metakaraktereket tartalmazó dokumentumok szövegrészeinek cseréjét. Ezzel a funkcióval speciális cseréket hajthat végre a dokumentumban, figyelembe véve a metakaraktereket.

#### K: Hogyan lehet új dokumentumot létrehozni az Aspose.Words for .NET-ben?

 V: A metakaraktereket tartalmazó szöveg cseréje funkció használata előtt létre kell hoznia egy új dokumentumot az Aspose.Words for .NET használatával. Ezt úgy lehet megtenni, hogy a`Document` tárgy. Íme egy mintakód egy új dokumentum létrehozásához:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### K: Hogyan lehet szöveget beszúrni egy dokumentumba az Aspose.Words for .NET használatával?

 V: Ha megvan a dokumentum, akkor a a segítségével illeszthet be szöveget`DocumentBuilder` tárgy. Példánkban a`Writeln` módszer több bekezdés szövegének különböző szakaszokba történő beillesztésére:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder.Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

#### K: Hogyan lehet konfigurálni a keresési és cserelehetőségeket az Aspose.Words for .NET-ben?

 V: Most konfiguráljuk a keresési és csere opciókat az a`FindReplaceOptions` tárgy. Példánkban a lecserélt bekezdések igazítását "Középre" állítottuk:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### K: Hogyan lehet metakaraktereket tartalmazó szöveget lecserélni egy dokumentumban az Aspose.Words for .NET használatával?

 V: Használjuk a`Range.Replace` módszer a metakaraktereket tartalmazó szöveg cseréjének végrehajtására. Példánkban a "szakasz" szó minden előfordulását, amelyet egy bekezdéstörés követ, lecseréljük ugyanazzal a szóval, amelyet több kötőjel követ, és egy új bekezdéstörés:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### K: Hogyan lehet lecserélni egy metakaraktereket tartalmazó egyéni szövegcímkét egy dokumentumban az Aspose.Words for .NET használatával?

 V: Mi is használjuk a`Range.Replace` módszer az egyéni "{insert-section}" szöveges címke szakasztöréssel. Példánkban a " "{insert-section}" és "&b"-vel szakasztörés beszúrásához:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### K: Hogyan lehet elmenteni a szerkesztett dokumentumot az Aspose.Words for .NET-be?

 V: Miután módosította a dokumentumot, elmentheti azt egy megadott könyvtárba a segítségével`Save` módszer:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```