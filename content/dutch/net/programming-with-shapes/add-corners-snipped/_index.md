---
title: Hoeken toevoegen, geknipt
linktitle: Hoeken toevoegen, geknipt
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een vorm met afgeknipte hoeken aan een Word-document kunt toevoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-shapes/add-corners-snipped/
---

 In deze zelfstudie wordt uitgelegd hoe u een vorm met afgeknipte hoeken aan een Word-document kunt toevoegen met Aspose.Words voor .NET. De afgeknipte hoeken kunnen worden aangepast en ingevoegd met behulp van de`InsertShape` methode.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"`met het daadwerkelijke pad naar de map waar u het document wilt opslaan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een nieuw document en DocumentBuilder
 Maak een nieuw exemplaar van de`Document` klasse en een`DocumentBuilder` bezwaar maken tegen het werken met het document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Plaats de afgeknipte vorm
 Gebruik de`InsertShape` werkwijze van de`DocumentBuilder` object om een vorm in te voegen waarvan de hoeken zijn afgeknipt. Geef het vormtype op (in dit geval`ShapeType.TopCornersSnipped`) en geef de gewenste maat voor de vorm op.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Stap 4: Sla het document op
 Sla het document op in de opgegeven map met behulp van de`Save`methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithShapes.AddCornersSnipped.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Voorbeeldbroncode voor Add Corners Geknipt met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

Dat is het! U hebt met succes een uit hoeken geknipte vorm aan uw Word-document toegevoegd met Aspose.Words voor .NET.