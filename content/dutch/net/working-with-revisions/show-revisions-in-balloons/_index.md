---
title: Toon revisies in ballonnen
linktitle: Toon revisies in ballonnen
second_title: Aspose.Words-API voor documentverwerking
description: Toon revisies in ballonnen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-revisions/show-revisions-in-balloons/
---

In deze stapsgewijze handleiding laten we u zien hoe u revisies in ballonnen in een Word-document kunt weergeven met Aspose.Words voor .NET. We voorzien u van de volledige broncode en laten u zien hoe u de markdown-uitvoer kunt formatteren.

## Stap 1: Het document laden

De eerste stap is het uploaden van het document met de revisies.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Stap 2: Configureer opties voor beoordelingsweergave

We zullen de weergaveopties configureren om revisies zichtbaar te maken in ballonnen.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Stap 3: Sla het document op in PDF-formaat

Ten slotte slaan we het document op als PDF, waarbij de revisies in ballonnen worden weergegeven.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Markdown-uitvoerformaten

De uitvoer kan in markdown worden opgemaakt om de leesbaarheid te verbeteren. Bijvoorbeeld :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Voorbeeldbroncode voor Show Revisions In Balloons met Aspose.Words voor .NET

Hier is de volledige broncode om revisies in ballonnen in een document weer te geven met Aspose.Words voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Rendert revisies inline in, verwijdert en formatteert revisies in ballonnen.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Rendert revisiebalken aan de rechterkant van een pagina.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u revisies in ballonnen in een Word-document kunt weergeven met behulp van Aspose.Words voor .NET. Door de juiste weergaveopties te gebruiken, konden we de revisies zichtbaar maken in bellen met revisiebalken aan de rechterkant. Aspose.Words voor .NET biedt veel krachtige functies voor het manipuleren van Word-documenten, inclusief revisiebeheer. Nu kunt u deze kennis gebruiken om revisies in ballonnen in uw eigen Word-documenten weer te geven met behulp van Aspose.Words voor .NET.


### Veelgestelde vragen

#### Vraag: Hoe upload ik een document in Aspose.Words voor .NET?

 EEN: Gebruik de`Document` klasse van Aspose.Words voor .NET om een document uit een bestand te laden. U kunt het volledige documentpad opgeven.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Vraag: Hoe kan ik revisies in ballonnen weergeven met Aspose.Words voor .NET?

 EEN: Gebruik de`ShowInBalloons` eigendom van de`RevisionOptions` object om de weergave van revisies in ballonnen te configureren. U kunt deze eigenschap inschakelen`ShowInBalloons.FormatAndDelete` om revisies in ballonnen weer te geven met verwijderings- en opmaakrevisies.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### Vraag: Hoe kan ik een document in PDF-formaat opslaan met Aspose.Words voor .NET?

 EEN: Gebruik de`Save` werkwijze van de`Document` object om het document in PDF-formaat op te slaan. U moet het volledige bestemmingspad opgeven met de extensie ".pdf".

```csharp
doc.Save("path/to/destination/document.pdf");
```