---
title: Voeg een bladwijzertekst toe aan een Word-document
linktitle: Voeg een bladwijzertekst toe aan een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u tekst uit een bladwijzer in een Word-document kunt toevoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/append-bookmarked-text/
---

In dit artikel zullen we de bovenstaande C#-broncode verkennen om te begrijpen hoe u de functie Append Bookmarked Text in de Aspose.Words voor .NET-bibliotheek kunt gebruiken. Met deze functie kunt u de tekst in een specifieke bladwijzer van een Word-document aan een ander document toevoegen.

## Vereisten

- Basiskennis van de C#-taal.
- .NET-ontwikkelomgeving met Aspose.Words-bibliotheek geïnstalleerd.

## Stap 1: Paragrafen uit bladwijzer halen

 Voordat we beginnen met het toevoegen van de bladwijzertekst, moeten we de alinea's ophalen die het begin en het einde van de bladwijzer bevatten. Dit kunt u doen door naar de`BookmarkStart` En`BookmarkEnd` eigenschappen van de bladwijzer:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Stap 2: Controleer de ouderparagrafen

We controleren of de begin- en eindparagrafen geldige ouders hebben, dat wil zeggen of ze echt bij een paragraaf horen. Als dit niet het geval is, genereren we een uitzondering:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Stap 3: Controleer de ouders van alinea's

We controleren of de begin- en eindparagrafen dezelfde ouder hebben. Als dat niet het geval is, betekent dit dat de paragrafen niet in dezelfde sectie of hetzelfde document voorkomen en dat er een uitzondering ontstaat:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Stap 4: Kopieer alinea's

We doorlopen de knooppunten (paragrafen) van de beginparagraaf tot de eindparagraaf. Voor elk knooppunt maken we een kopie en importeren deze in de context van het bestemmingsdocument:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Voorbeeldbroncode voor het toevoegen van tekst met bladwijzer met Aspose.Words voor .NET

Hier is de volledige voorbeeldbroncode om te demonstreren dat u tekst uit een bladwijzer kunt toevoegen met Aspose.Words voor .NET:

```csharp

	// Dit is de paragraaf die het begin van de bladwijzer bevat.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// Dit is de paragraaf die het einde van de bladwijzer bevat.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Beperk ons tot een redelijk eenvoudig scenario.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// We willen alle paragrafen kopiëren vanaf de beginparagraaf tot (en inclusief) de eindparagraaf,
	// daarom is het knooppunt waar we stoppen er één na de eindparagraaf.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//Hierdoor wordt een kopie gemaakt van het huidige knooppunt en wordt deze geïmporteerd (maakt deze geldig) in de context
		// van het bestemmingsdocument. Importeren betekent dat stijlen en lijst-ID's correct worden aangepast.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u de functie Append Bookmarked Text van Aspose.Words voor .NET kunt gebruiken. We hebben een stapsgewijze handleiding gevolgd voor het ophalen van alinea's uit een bladwijzer, het verifiëren van bovenliggende alinea's en het kopiëren van alinea's naar een ander document.

### Veelgestelde vragen over het toevoegen van tekst met een bladwijzer aan een Word-document

#### V1: Wat zijn de vereisten om de functie "Tekst met bladwijzers toevoegen" in Aspose.Words voor .NET te gebruiken?

A: Om de functie "Tekst met bladwijzers toevoegen" in Aspose.Words voor .NET te gebruiken, hebt u basiskennis van de C#-taal nodig. U hebt ook een .NET-ontwikkelomgeving nodig waarin de Aspose.Words-bibliotheek is geïnstalleerd.

#### Vraag 2: Hoe krijg ik de alinea's met het begin en einde van een bladwijzer in een Word-document?

A: Om de paragrafen met het begin en einde van een bladwijzer in een Word-document te krijgen, kunt u toegang krijgen tot de`BookmarkStart` En`BookmarkEnd` eigenschappen van de bladwijzer. Hier is een voorbeeldcode:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Vraag 3: Wat gebeurt er als de begin- en eindparagrafen geen geldige ouders hebben?

A: Als de begin- en eindparagrafen geen geldige bovenliggende alinea's hebben, dwz het zijn niet echt alinea's, wordt er een uitzondering gegenereerd. Deze situatie kan op dit moment niet worden beheerd.
