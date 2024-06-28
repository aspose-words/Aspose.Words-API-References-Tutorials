---
title: Verticaal anker
linktitle: Verticaal anker
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een vorm verticaal in een document plaatst met behulp van de verticale ankerfunctie in Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-shapes/vertical-anchor/
---

In deze zelfstudie wordt uitgelegd hoe u de verticale ankerfunctie in Aspose.Words voor .NET gebruikt om een vorm verticaal in een document te positioneren. Door de verticale ankereigenschap van een vorm in te stellen, kunt u de verticale uitlijning ten opzichte van de tekst of de pagina bepalen.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar u het document wilt opslaan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een nieuw document en DocumentBuilder
 Maak een nieuw exemplaar van de`Document` klasse en een`DocumentBuilder` bezwaar maken tegen het werken met het document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Een vorm invoegen en configureren
 Voeg een vorm in het document in met behulp van de`InsertShape` werkwijze van de`DocumentBuilder` voorwerp. Stel de gewenste afmetingen voor de vorm in.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Stap 4: Stel het verticale anker in
Stel de verticale ankereigenschap van de vorm in om de verticale uitlijning ervan te bepalen. In dit voorbeeld stellen we dit in op 'Onder' om de vorm onderaan de tekst of pagina te verankeren.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Stap 5: Voeg inhoud toe aan de vorm
 Gebruik de`MoveTo` werkwijze van de`DocumentBuilder` object om de cursor naar de eerste alinea van de vorm te verplaatsen. Gebruik dan de`Write` methode om inhoud aan de vorm toe te voegen.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Stap 6: Sla het document op
 Sla het document op in de opgegeven map met behulp van de`Save`methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithShapes.VerticalAnchor.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Voorbeeldbroncode voor verticaal anker met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

Dat is het! U hebt met succes de verticale ankerfunctie in Aspose.Words voor .NET gebruikt om een vorm verticaal in een document te positioneren.