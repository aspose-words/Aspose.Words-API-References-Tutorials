---
title: Könyvjelzővel ellátott szöveg hozzáfűzése a Word-dokumentumhoz
linktitle: Könyvjelzővel ellátott szöveg hozzáfűzése a Word-dokumentumhoz
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan adhat hozzá szöveget egy könyvjelzőből egy Word-dokumentumhoz az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-bookmarks/append-bookmarked-text/
---

Ebben a cikkben megvizsgáljuk a fenti C# forráskódot, hogy megértsük, hogyan használhatjuk a Könyvjelzővel ellátott szöveg hozzáfűzése funkciót az Aspose.Words for .NET könyvtárban. Ez a funkció lehetővé teszi, hogy egy Word-dokumentum adott könyvjelzőjében található szöveget hozzáadja egy másik dokumentumhoz.

## Előfeltételek

- C# nyelv alapismerete.
- .NET fejlesztői környezet telepített Aspose.Words könyvtárral.

## 1. lépés: Bekezdések lekérése a könyvjelzőből

 Mielőtt elkezdenénk hozzáadni a könyvjelző szövegét, be kell szereznünk azokat a bekezdéseket, amelyek a könyvjelző elejét és végét tartalmazzák. Ezt megteheti a`BookmarkStart` és`BookmarkEnd` a könyvjelző tulajdonságai:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## 2. lépés: Ellenőrizze a szülő bekezdéseket

Ellenőrizzük, hogy az eleje és a záró bekezdésnek van-e érvényes szülője, vagyis valóban egy bekezdéshez tartozik-e. Ha nem, kivételt generálunk:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## 3. lépés: Ellenőrizze a bekezdések szüleit

Ellenőrizzük, hogy a kezdő és a záró bekezdésnek ugyanaz a szülője. Ha nem, az azt jelenti, hogy a bekezdések nem ugyanabban a szakaszban vagy dokumentumban találhatók, és kivételt teszünk:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## 4. lépés: Bekezdések másolása

Iterálunk a csomópontokon (bekezdéseken) a kezdő bekezdéstől a befejező bekezdésig. Minden csomóponthoz létrehozunk egy másolatot, és importáljuk a céldokumentum kontextusába:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Példa forráskódra a Könyvjelzővel ellátott szöveg hozzáfűzéséhez az Aspose.Words for .NET használatával

Íme a teljes példaforráskód, amely bemutatja, hogyan lehet szöveget hozzáadni egy könyvjelzőből az Aspose.Words for .NET használatával:

```csharp

	// Ez az a bekezdés, amely a könyvjelző elejét tartalmazza.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// Ez az a bekezdés, amely a könyvjelző végét tartalmazza.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Korlátozzuk magunkat egy ésszerűen egyszerű forgatókönyvre.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// Minden bekezdést át akarunk másolni a kezdő bekezdéstől a záró bekezdésig (beleértve),
	// ezért a csomópont, amelynél megállunk, egy a bekezdés végének után van.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//Ez létrehozza az aktuális csomópont másolatát, és importálja (érvényessé teszi) a kontextusba
		// a rendeltetési okmány. Az importálás a stílusok és a listaazonosítók helyes beállítását jelenti.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Következtetés

Ebben a cikkben megvizsgáltuk a C# forráskódot, hogy megértsük, hogyan használható az Aspose.Words for .NET Könyvjelzővel ellátott szöveg hozzáfűzése funkciója. Követtünk egy lépésről lépésre szóló útmutatót a bekezdések könyvjelzőből való lekéréséhez, a szülők ellenőrzéséhez és a bekezdések másik dokumentumba másolásához.

### GYIK a könyvjelzővel ellátott szöveg hozzáfűzéséhez a Word dokumentumban

#### 1. kérdés: Milyen előfeltételei vannak az Aspose.Words for .NET "Szöveg hozzáadása könyvjelzőkkel" funkciójának használatához?

V: Az Aspose.Words for .NET "Szöveg hozzáadása könyvjelzőkkel" funkciójának használatához alapszintű C# nyelvtudással kell rendelkeznie. Szüksége van egy .NET fejlesztői környezetre is, amelyen az Aspose.Words könyvtár telepítve van.

#### 2. kérdés: Hogyan lehet beolvasni azokat a bekezdéseket, amelyek egy könyvjelző elejét és végét tartalmazzák egy Word-dokumentumban?

V: A könyvjelző elejét és végét tartalmazó bekezdések megjelenítéséhez egy Word-dokumentumban elérheti a`BookmarkStart` és`BookmarkEnd` a könyvjelző tulajdonságait. Itt van egy minta kód:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### 3. kérdés: Mi történik, ha a kezdő és a záró bekezdésnek nincs érvényes szülője?

V: Ha a kezdő és záró bekezdésnek nincs érvényes szülője, azaz valójában nem bekezdések, akkor kivételt dobunk. Ez a helyzet jelenleg nem kezelhető.
