---
title: Voeg een bladwijzertekst toe aan een Word-document
linktitle: Voeg een bladwijzertekst toe aan een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer met deze stapsgewijze handleiding hoe u tekst met een bladwijzer aan een Word-document kunt toevoegen met Aspose.Words voor .NET. Ideaal voor ontwikkelaars.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/append-bookmarked-text/
---
## Invoering

Hallo daar! Heeft u ooit geprobeerd tekst toe te voegen uit een gedeelte met een bladwijzer in een Word-document en vond u dit lastig? Je hebt geluk! In deze zelfstudie wordt u door het proces geleid met Aspose.Words voor .NET. We zullen het in eenvoudige stappen opsplitsen, zodat u het gemakkelijk kunt volgen. Laten we erin duiken en die tekst met bladwijzer als een professional toevoegen!

## Vereisten

Voordat we beginnen, zorgen we ervoor dat u alles heeft wat u nodig heeft:

-  Aspose.Words voor .NET: Zorg ervoor dat je het geïnstalleerd hebt. Zo niet, dan kan dat[download het hier](https://releases.aspose.com/words/net/).
- Ontwikkelomgeving: Elke .NET-ontwikkelomgeving zoals Visual Studio.
- Basiskennis van C#: Het begrijpen van de basisconcepten van C#-programmeren zal helpen.
- Word-document met bladwijzers: een Word-document met bladwijzers, dat we zullen gebruiken om tekst aan toe te voegen.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren. Dit zorgt ervoor dat we alle tools die we nodig hebben binnen handbereik hebben.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Importing;
```

Laten we het voorbeeld opsplitsen in gedetailleerde stappen.

## Stap 1: Laad het document en initialiseer variabelen

Oké, laten we beginnen met het laden van ons Word-document en het initialiseren van de variabelen die we nodig hebben.

```csharp
// Laad de bron- en doeldocumenten.
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");

// Initialiseer de documentimporteur.
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

// Zoek de bladwijzer in het brondocument.
Bookmark srcBookmark = srcDoc.Range.Bookmarks["YourBookmarkName"];
```

## Stap 2: Identificeer de begin- en eindparagrafen

Laten we nu de alinea's zoeken waar de bladwijzer begint en eindigt. Dit is van cruciaal belang omdat we de tekst binnen deze grenzen moeten behandelen.

```csharp
// Dit is de paragraaf die het begin van de bladwijzer bevat.
Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;

// Dit is de paragraaf die het einde van de bladwijzer bevat.
Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

if (startPara == null || endPara == null)
    throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");
```

## Stap 3: Valideer alinea-ouders

We moeten ervoor zorgen dat de begin- en eindparagrafen dezelfde ouder hebben. Dit is een eenvoudig scenario om de zaken overzichtelijk te houden.

```csharp
// Beperk ons tot een redelijk eenvoudig scenario.
if (startPara.ParentNode != endPara.ParentNode)
    throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");
```

## Stap 4: Identificeer het knooppunt dat moet worden gestopt

Vervolgens moeten we het knooppunt bepalen waar we stoppen met het kopiëren van tekst. Dit is het knooppunt onmiddellijk na de eindparagraaf.

```csharp
// We willen alle paragrafen kopiëren vanaf de beginparagraaf tot (en inclusief) de eindparagraaf,
// daarom is het knooppunt waar we stoppen er één na de eindparagraaf.
Node endNode = endPara.NextSibling;
```

## Stap 5: Voeg een tekst met bladwijzer toe aan het doeldocument

Laten we ten slotte de knooppunten doorlopen vanaf de startparagraaf tot het knooppunt na de eindparagraaf, en deze aan het doeldocument toevoegen.

```csharp
for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
    // Hierdoor wordt een kopie gemaakt van het huidige knooppunt en wordt deze geïmporteerd (maakt deze geldig) in de context
    // van het bestemmingsdocument. Importeren betekent dat stijlen en lijst-ID's correct worden aangepast.
    Node newNode = importer.ImportNode(curNode, true);

    // Voeg het geïmporteerde knooppunt toe aan het doeldocument.
    dstDoc.FirstSection.Body.AppendChild(newNode);
}

// Sla het doeldocument op met de toegevoegde tekst.
dstDoc.Save("appended_document.docx");
```

## Conclusie

En daar heb je het! U hebt met succes tekst uit een sectie met een bladwijzer in een Word-document toegevoegd met Aspose.Words voor .NET. Met deze krachtige tool wordt het manipuleren van documenten een fluitje van een cent, en nu heb je nog een truc achter de hand. Veel codeerplezier!

## Veelgestelde vragen

### Kan ik tekst uit meerdere bladwijzers in één keer toevoegen?
Ja, u kunt het proces voor elke bladwijzer herhalen en de tekst dienovereenkomstig toevoegen.

### Wat moet ik doen als de begin- en eindparagrafen verschillende ouders hebben?
In het huidige voorbeeld wordt ervan uitgegaan dat ze dezelfde ouder hebben. Voor verschillende ouders is een complexere afhandeling vereist.

### Kan ik de originele opmaak van de toegevoegde tekst behouden?
 Absoluut! De`ImportFormatMode.KeepSourceFormatting` zorgt ervoor dat de originele opmaak behouden blijft.

### Is het mogelijk om tekst toe te voegen aan een specifieke positie in het bestemmingsdocument?
Ja, u kunt de tekst op elke positie toevoegen door naar het gewenste knooppunt in het doeldocument te navigeren.

### Wat moet ik doen als ik tekst uit een bladwijzer aan een nieuwe sectie moet toevoegen?
U kunt een nieuwe sectie in het doeldocument maken en de tekst daar toevoegen.