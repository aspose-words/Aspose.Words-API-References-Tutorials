---
title: Horizontaal regelformaat in Word-document
linktitle: Horizontaal regelformaat in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u horizontale regels in Word-documenten opmaakt met Aspose.Words voor .NET. Stap-voor-stap handleiding.
type: docs
weight: 10
url: /nl/net/add-content-using-documentbuilder/horizontal-rule-format/
---
In dit uitgebreide voorbeeld leert u hoe u een horizontale regel in een Word-document kunt opmaken met Aspose.Words voor .NET. Wij begeleiden u door het proces en voorzien u van de benodigde C#-codefragmenten. Aan het einde van deze handleiding kunt u de uitlijning, breedte, hoogte, kleur en andere eigenschappen van een horizontale lijn aanpassen.

## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Aspose.Words voor .NET-bibliotheek geïnstalleerd op uw systeem.

## Stap 1: Maak een DocumentBuilder en voeg een horizontale lijn in
Maak om te beginnen een DocumentBuilder-object en gebruik de InsertHorizontalRule-methode om een horizontale regel in te voegen:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Stap 2: Open het horizontale regelformaat
Ga vervolgens naar de eigenschap HorizontalRuleFormat van het Shape-object om de opmaakopties op te halen:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Stap 3: Pas de opmaakopties aan
Nu kunt u verschillende opmaakopties voor de horizontale regel aanpassen. U kunt bijvoorbeeld de uitlijning, breedte, hoogte, kleur en arcering aanpassen:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Stap 4: Sla het document op
Nadat u de horizontale lijn hebt opgemaakt, slaat u het document op in een bestand met behulp van de Save-methode van het Document-object:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Voorbeeldbroncode voor horizontale regelindeling met Aspose.Words voor .NET
Hier is de volledige broncode voor het formatteren van een horizontale regel met Aspose.Words voor .NET:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

Vergeet niet om de code aan te passen aan uw specifieke vereisten en deze indien nodig uit te breiden met extra functionaliteit.

## Conclusie
Gefeliciteerd! Je hebt met succes geleerd hoe je een horizontale regel in een Word-document kunt opmaken met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u nu het uiterlijk van horizontale regels aanpassen om de visuele lay-out van uw document te verbeteren.

Experimenteer met verschillende opmaakopties om de gewenste stijl en het gewenste effect voor uw horizontale regels te bereiken.

### Veelgestelde vragen over het formaat van horizontale regels in een Word-document

#### Vraag: Kan ik verschillende kleuren toepassen op de horizontale regel?

EEN: Absoluut! Met Aspose.Words voor .NET kunt u de kleur van de horizontale lijn eenvoudig aanpassen door de eigenschap Color in te stellen op de gewenste kleurwaarde. Hierdoor kunt u de horizontale lijn afstemmen op het algehele ontwerp van uw document.

#### Vraag: Is het mogelijk om de breedte en hoogte van de horizontale regel aan te passen?

A: Ja, u heeft volledige controle over de breedte en hoogte van de horizontale regel. Door de eigenschappen BreedtePercent en Hoogte te wijzigen, kunt u de gewenste afmetingen voor de horizontale regel bereiken.

#### Vraag: Kan ik de uitlijning van de horizontale lijn in het document wijzigen?

EEN: Zeker! Met Aspose.Words voor .NET kunt u de uitlijning van de horizontale regel opgeven met behulp van de eigenschap Alignment. U kunt kiezen uit verschillende opties, zoals Midden, Links, Rechts en Uitgevuld.

#### Vraag: Kan ik schaduw of achtergrondkleur toepassen op de horizontale regel?

A: Ja, u kunt schaduw of achtergrondkleur toevoegen aan de horizontale lijn. Standaard is de eigenschap NoShade ingesteld op true, maar u kunt deze instellen op false en de arcering definiëren met behulp van de juiste methoden.

#### Vraag: Kan ik meerdere horizontale regels in één document invoegen?

EEN: Absoluut! U kunt meerdere horizontale regels in een Word-document invoegen met Aspose.Words voor .NET. Herhaal eenvoudigweg de stappen in de tutorial als dat nodig is om zoveel horizontale regels toe te voegen als u nodig heeft.