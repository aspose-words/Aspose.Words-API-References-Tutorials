---
title: Könyvjelzővel ellátott tartalom elrejtése a Word-dokumentumban
linktitle: Könyvjelzővel ellátott tartalom elrejtése a Word-dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan jeleníthet meg vagy rejthet el könyvjelzőket a Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

Ebben a cikkben megvizsgáljuk a fenti C#-forráskódot, hogy megértsük, hogyan kell használni a Könyvjelzők elrejtése funkciót az Aspose.Words for .NET könyvtárban. Ez a funkció lehetővé teszi egy könyvjelző tartalmának megjelenítését vagy elrejtését a Word-dokumentumban egy adott feltétel alapján az adatok egyesítésekor.

## Előfeltételek

- C# nyelv alapismerete.
- .NET fejlesztői környezet telepített Aspose.Words könyvtárral.

## 1. lépés: A könyvjelző lekérése

 Használjuk a`Bookmarks` a dokumentumtartomány tulajdonsága, hogy megkapjuk azt a könyvjelzőt, amelyen a tartalmat meg szeretnénk jeleníteni vagy elrejteni:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## 2. lépés: Az egyesítési mezők beszúrása

 Dokumentumkészítőt használunk`DocumentBuilder` a szükséges egyesítési mezők beszúrásához. Ezek az egyesítési mezők feltételt állítanak be a könyvjelző tartalmának megjelenítésére vagy elrejtésére, az értéktől függően`showHide` változó:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## 3. lépés: A könyvjelző tartalmának áthelyezése

Végigpörgetjük a könyvjelző tartalmát, és úgy mozgatjuk, hogy megjelenjen

isse a könyvjelző előtt. Ez szabályozza a tartalom megjelenítését vagy elrejtését a megadott feltétel alapján:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## 4. lépés: A könyvjelző többi részének áthelyezése

könyvjelző többi részét áthelyezzük a könyvjelző után, beszúrási pontként a könyvjelző végcsomópontját használva:

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## 5. lépés: Az egyesítés végrehajtása

 Használjuk a`Execute` a dokumentum módszere`s `Körlevél` object to execute the merge using the bookmark name and the value of the `showHide` változó:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Példa forráskódra a Könyvjelzővel ellátott tartalom elrejtése Aspose.Words for .NET használatával funkcióhoz

Íme a teljes példa a forráskódra, amely bemutatja a könyvjelzők tartalmának megjelenítését vagy elrejtését az Aspose.Words for .NET használatával:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD könyvjelző}" = "igaz" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## Következtetés

Ebben a cikkben megvizsgáltuk a C# forráskódot, hogy megértsük, hogyan használható az Aspose.Words for .NET Könyvjelzők elrejtése funkciója. Követtünk egy lépésenkénti útmutatót a könyvjelzők tartalmának megjelenítéséhez vagy elrejtéséhez egy adott feltétel alapján az adatok egyesítésekor.

### A könyvjelzővel ellátott tartalom elrejtése a Word dokumentumban a megjelenítéssel kapcsolatos GYIK

#### K: Használhatom ugyanazt a feltételt több könyvjelzőhöz ugyanabban a dokumentumban?

V: Igen, ugyanazt a feltételt használhatja több könyvjelzőhöz ugyanabban a dokumentumban. Csak ismételje meg a 2-5. lépéseket minden könyvjelzőnél, módosítsa a könyvjelző nevét és opcionálisan a értékét`showhide` szükség szerint változtatható.

#### K: Hogyan adhatok hozzá további feltételeket a könyvjelzők tartalmának megjelenítéséhez vagy elrejtéséhez?

 V: További feltételek hozzáadásához használhat logikai operátorokat, mint pl`AND` és`OR` a 2. lépésben az egyesítési mezők beillesztéséhez szükséges kódban. Szerkessze a feltételt a következő kódban további feltételek hozzáadásához:

```csharp
builder. Write("\" = \"true\" ");
```

#### K: Hogyan törölhetek egy könyvjelzőt egy Word-dokumentumból az Aspose.Words for .NET használatával?

 V: Könyvjelző eltávolításához Word-dokumentumból az Aspose.Words for .NET használatával, használja a`Remove` módszer a`Bookmarks` dokumentumtartomány gyűjteménye. Íme egy mintakód egy adott könyvjelző törléséhez:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### K: Ingyenes az Aspose.Words könyvtár?

 V: Az Aspose.Words könyvtár kereskedelmi célú könyvtár, és a projektekben való használatához érvényes licenc szükséges. Ellenőrizheted[Aspose.Words .NET API hivatkozásokhoz](https://reference.aspose.com/words/net/) hogy többet megtudjon az engedélyezési lehetőségekről és az árakról.

#### K: Vannak más könyvtárak is a Word-dokumentumokkal végzett szövegfeldolgozáshoz a .NET-ben?

V: Igen, más könyvtárak is elérhetők a Word-dokumentumokkal végzett szövegfeldolgozáshoz a .NET-ben, például az Open XML SDK és a GemBox.Document. Ezeket a könyvtárakat az Aspose.Words alternatívájaként fedezheti fel sajátos igényei és preferenciái alapján.