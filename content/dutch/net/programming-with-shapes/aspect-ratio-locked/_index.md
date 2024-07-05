---
title: Beeldverhouding vergrendeld
linktitle: Beeldverhouding vergrendeld
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de beeldverhouding van een vorm in een Word-document kunt vergrendelen of ontgrendelen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-shapes/aspect-ratio-locked/
---

In deze zelfstudie wordt uitgelegd hoe u de beeldverhouding van een vorm in een Word-document kunt vergrendelen of ontgrendelen met Aspose.Words voor .NET. Door de beeldverhouding te vergrendelen, kunt u de oorspronkelijke verhoudingen van de vorm behouden wanneer u het formaat ervan wijzigt.

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
 Maak een nieuw exemplaar van de`Document` klasse en een`DocumentBuilder`bezwaar maken tegen het werken met het document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Voeg een afbeeldingsvorm in
 Gebruik de`InsertImage` werkwijze van de`DocumentBuilder` object om een afbeeldingsvorm in het document in te voegen. Geef het pad naar het afbeeldingsbestand op als parameter.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Stap 4: Vergrendel of ontgrendel de beeldverhouding
 Stel de`AspectRatioLocked` eigenschap van de vorm`true` of`false` om respectievelijk de beeldverhouding te vergrendelen of ontgrendelen.

```csharp
shape.AspectRatioLocked = false; //Ontgrendel de beeldverhouding
```

## Stap 5: Sla het document op
 Sla het document op in de opgegeven map met behulp van de`Save` methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithShapes.AspectRatioLocked.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Voorbeeldbroncode voor Aspect Ratio Locked met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

Dat is het! U hebt de beeldverhouding van een vorm in uw Word-document met succes vergrendeld of ontgrendeld met Aspose.Words voor .NET.