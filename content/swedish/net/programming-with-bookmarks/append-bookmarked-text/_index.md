---
title: Lägg till bokmärkt text i Word-dokument
linktitle: Lägg till bokmärkt text i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du lägger till text från ett bokmärke i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/append-bookmarked-text/
---

I den här artikeln kommer vi att utforska ovanstående C#-källkod för att förstå hur man använder funktionen Lägg till bokmärkt text i Aspose.Words för .NET-biblioteket. Med den här funktionen kan du lägga till texten i ett specifikt bokmärke i ett Word-dokument till ett annat dokument.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Få stycken från bokmärket

 Innan vi börjar lägga till bokmärkestexten måste vi få fram styckena som innehåller början och slutet av bokmärket. Detta kan göras genom att gå till`BookmarkStart` och`BookmarkEnd` egenskaper för bokmärket:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Steg 2: Kontrollera överordnade stycken

Vi kontrollerar om början och slutstycket har giltiga föräldrar, det vill säga om de verkligen tillhör ett stycke. Om inte genererar vi ett undantag:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Steg 3: Kontrollera föräldrar till stycken

Vi kontrollerar om början och slutet av stycket har samma förälder. Om inte, betyder det att styckena inte finns i samma avsnitt eller dokument, och vi gör ett undantag:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Steg 4: Kopiera stycken

Vi itererar genom noderna (styckena) från startstycket till slutstycket. För varje nod skapar vi en kopia och importerar den till måldokumentets sammanhang:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Exempel på källkod för Lägg till bokmärkt text med Aspose.Words för .NET

Här är den fullständiga källkoden som visar hur man lägger till text från ett bokmärke med Aspose.Words för .NET:

```csharp

	// Detta är stycket som innehåller början av bokmärket.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// Detta är stycket som innehåller slutet av bokmärket.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Begränsa oss till ett ganska enkelt scenario.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// Vi vill kopiera alla stycken från startstycket till (och inklusive) slutstycket,
	// därför är noden där vi stannar en efter slutstycket.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		// Detta skapar en kopia av den aktuella noden och importerar den (gör den giltig) i sammanhanget
		// av destinationsdokumentet. Importering innebär att anpassa stilar och listidentifierare korrekt.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Slutsats

I den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen Lägg till bokmärkt text i Aspose.Words för .NET. Vi har följt en steg-för-steg-guide för att hämta stycken från ett bokmärke, verifiera föräldrar och kopiera stycken till ett annat dokument.

### Vanliga frågor för att lägga till bokmärkt text i Word-dokument

#### F1: Vilka är förutsättningarna för att använda funktionen "Lägg till text med bokmärken" i Aspose.Words för .NET?

S: För att använda funktionen "Lägg till text med bokmärken" i Aspose.Words för .NET behöver du ha grundläggande kunskaper i C#-språket. Du behöver också en .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

#### F2: Hur får man de stycken som innehåller början och slutet av ett bokmärke i ett Word-dokument?

 S: För att få de stycken som innehåller början och slutet av ett bokmärke i ett Word-dokument kan du komma åt`BookmarkStart` och`BookmarkEnd` egenskaper för bokmärket. Här är en exempelkod:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### F3: Vad händer om start- och slutstyckena inte har giltiga föräldrar?

S: Om start- och slutstyckena inte har giltiga föräldrar, dvs de är inte riktigt stycken, kommer ett undantag att kastas. Denna situation kan inte hanteras i nuläget.
