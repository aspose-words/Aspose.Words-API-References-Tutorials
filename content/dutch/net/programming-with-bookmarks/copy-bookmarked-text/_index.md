---
title: Kopieer de tekst met bladwijzer naar een Word-document
linktitle: Kopieer de tekst met bladwijzer naar een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u bladwijzertekst in een Word-document naar een ander document kunt kopiëren met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/copy-bookmarked-text/
---

In dit artikel zullen we de bovenstaande C#-broncode verkennen om te begrijpen hoe u de functie Copy Bookmarked Text in de Aspose.Words voor .NET-bibliotheek kunt gebruiken. Met deze functie kunt u de inhoud van een specifieke bladwijzer van een brondocument naar een ander document kopiëren.

## Vereisten

- Basiskennis van de C#-taal.
- .NET-ontwikkelomgeving met Aspose.Words-bibliotheek geïnstalleerd.

## Stap 1: Brondocument laden

 Voordat we de bladwijzertekst kopiëren, moeten we het brondocument in een`Document` object met behulp van het bestandspad:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Stap 2: Bronbladwijzer ophalen

 Wij gebruiken de`Bookmarks` eigenschap van het brondocumentbereik om de specifieke bladwijzer te krijgen die we willen kopiëren:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Stap 3: Het doeldocument aanmaken

We maken een nieuw document dat zal dienen als het bestemmingsdocument om de bladwijzerinhoud te kopiëren:

```csharp
Document dstDoc = new Document();
```

## Stap 4: De kopieerlocatie opgeven

We specificeren de locatie waar we de gekopieerde tekst willen toevoegen. In ons voorbeeld voegen we de tekst toe aan het einde van de hoofdtekst van de laatste sectie van het doeldocument:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Stap 5: Importeer en kopieer bladwijzertekst

 Wij gebruiken een`NodeImporter`object om bladwijzertekst te importeren en kopiëren van een brondocument naar het doeldocument:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Voorbeeldbroncode voor het kopiëren van tekst met bladwijzer met Aspose.Words voor .NET

Hier is de volledige voorbeeldbroncode om het kopiëren van tekst uit een bladwijzer te demonstreren met Aspose.Words voor .NET:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Dit is de bladwijzer waarvan we de inhoud willen kopiëren.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Wij zullen dit document aanvullen.
	Document dstDoc = new Document();

	// Laten we zeggen dat we worden toegevoegd aan het einde van de hoofdtekst van de laatste sectie.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Als u meerdere keren importeert zonder een enkele context, zal dit ertoe leiden dat er veel stijlen worden gemaakt.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### VoegBookmarkedText-broncode toe

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
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
        }

```
## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u de functie Copy Bookmarked Text from Aspose.Words voor .NET kunt gebruiken. We volgden een stapsgewijze handleiding om de inhoud van een bladwijzer van een brondocument naar een ander document te kopiëren.

### Veelgestelde vragen over het kopiëren van tekst met een bladwijzer in een Word-document

#### Vraag: Wat zijn de vereisten om de functie "Tekst met bladwijzers kopiëren" in Aspose.Words voor .NET te gebruiken?

A: Om de functie "Tekst met bladwijzers kopiëren" in Aspose.Words voor .NET te gebruiken, hebt u basiskennis van de C#-taal nodig. U hebt ook een .NET-ontwikkelomgeving nodig waarin de Aspose.Words-bibliotheek is geïnstalleerd.

#### Vraag: Hoe laad ik een brondocument in Aspose.Words voor .NET?

 A: Om een brondocument in Aspose.Words voor .NET te laden, kunt u de`Document` klasse door het bestandspad van het document op te geven. Hier is een voorbeeldcode:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### Vraag: Hoe krijg ik de inhoud van een specifieke bladwijzer in een brondocument met Aspose.Words voor .NET?

 A: Om de inhoud van een specifieke bladwijzer in een brondocument op te halen met Aspose.Words voor .NET, kunt u toegang krijgen tot de`Bookmarks` eigenschap van het brondocumentbereik en gebruik de bladwijzernaam om de specifieke bladwijzer op te halen. Hier is een voorbeeldcode:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### Vraag: Hoe kan ik de locatie van de bladwijzertekstkopie in een doeldocument opgeven met Aspose.Words voor .NET?

 A: Om op te geven waar u gekopieerde bladwijzertekst wilt toevoegen in een doeldocument met behulp van Aspose.Words voor .NET, kunt u naar de hoofdtekst van de laatste sectie van het doeldocument navigeren. U kunt gebruik maken van de`LastSection` eigenschap om toegang te krijgen tot het laatste gedeelte en de`Body` eigenschap om toegang te krijgen tot de hoofdtekst van die sectie. Hier is een voorbeeldcode:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### Vraag: Hoe kan ik bladwijzertekst importeren en kopiëren van het brondocument naar het doeldocument met Aspose.Words voor .NET?

 A: Om bladwijzertekst te importeren en kopiëren van een brondocument naar een doeldocument met behulp van Aspose.Words voor .NET, kunt u de`NodeImporter` klasse die het brondocument, het doeldocument en de te behouden opmaakmodus specificeert. Dan kun je gebruik maken van de`AppendBookmarkedText` methode om de bladwijzertekst toe te voegen aan het doeldocument. Hier is een voorbeeldcode:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### Vraag: Hoe kan ik een doeldocument opslaan na het kopiëren van bladwijzertekst met Aspose.Words voor .NET?

A: Om een doeldocument op te slaan na het kopiëren van tekst uit een bladwijzer met Aspose.Words voor .NET, kunt u de`Save` werkwijze van de`Document` object dat het doelbestandspad specificeert. Hier is een voorbeeldcode:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```