---
title: Zwevende afbeelding invoegen in Word-document
linktitle: Zwevende afbeelding invoegen in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u zwevende afbeeldingen invoegt in Word-documenten met Aspose.Words voor .NET. Stap-voor-stap handleiding.
type: docs
weight: 10
url: /nl/net/add-content-using-documentbuilder/insert-floating-image/
---
In dit uitgebreide voorbeeld leert u hoe u een zwevende afbeelding in een Word-document kunt invoegen met Aspose.Words voor .NET. Wij begeleiden u door het proces en voorzien u van de benodigde C#-codefragmenten. Aan het einde van deze handleiding kunt u afbeeldingen met aanpasbare positionerings- en terugloopopties aan uw documenten toevoegen.

## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Aspose.Words voor .NET-bibliotheek geïnstalleerd op uw systeem.

## Stap 1: Maak een nieuw document en DocumentBuilder
Maak om te beginnen een nieuw document met behulp van de klasse Document en initialiseer een DocumentBuilder-object:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Voeg een zwevende afbeelding in
Gebruik vervolgens de InsertImage-methode van de DocumentBuilder-klasse om een zwevende afbeelding in te voegen. Geef het afbeeldingsbestandspad, de relatieve horizontale en verticale positie, breedte, hoogte en terugloopopties op als parameters:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## Stap 3: Sla het document op
Nadat u de zwevende afbeelding hebt ingevoegd, slaat u het document op in een bestand met behulp van de Save-methode van de Document-klasse:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Voorbeeldbroncode voor het invoegen van een zwevende afbeelding met Aspose.Words voor .NET
Hier is de volledige broncode voor het invoegen van een zwevende afbeelding met Aspose.Words voor .NET:
Zwevende afbeeldingen zijn handig voor verschillende scenario's, zoals het toevoegen van logo's, illustraties of decoratieve elementen die onafhankelijk van de tekst van het document kunnen worden geplaatst.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

Vergeet niet om de code aan te passen aan uw specifieke vereisten, inclusief het pad naar het afbeeldingsbestand en de gewenste positionerings- en terugloopopties.

## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u een zwevende afbeelding in een Word-document kunt invoegen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u uw documenten nu verfraaien met visueel aantrekkelijke en aanpasbare zwevende afbeeldingen.

### Veelgestelde vragen over het invoegen van een zwevende afbeelding in een Word-document

#### Vraag: Kan ik meerdere zwevende afbeeldingen in één document invoegen?

EEN: Zeker! U kunt zoveel zwevende afbeeldingen als nodig in een Word-document invoegen met Aspose.Words voor .NET. Herhaal eenvoudigweg het invoegproces om meerdere visueel aantrekkelijke afbeeldingen toe te voegen.

#### Vraag: Welke omloopopties zijn beschikbaar voor de zwevende afbeelding?

A: Aspose.Words voor .NET biedt verschillende terugloopopties voor zwevende afbeeldingen, waaronder Square, Tight, Through, TopBottom en Geen. Deze opties bepalen hoe de tekst interageert met de zwevende afbeelding.

#### Vraag: Kan ik de grootte van de zwevende afbeelding aanpassen?

EEN: Absoluut! U kunt de breedte en hoogte van de zwevende afbeelding opgeven met behulp van de respectieve parameters in de InsertImage-methode. Hierdoor kunt u de afmetingen van de afbeelding bepalen volgens uw ontwerpvoorkeuren.

#### Vraag: Kan ik de zwevende afbeelding positioneren ten opzichte van een specifiek element in het document?

A: Ja, met Aspose.Words voor .NET kunt u de zwevende afbeelding positioneren ten opzichte van specifieke elementen, zoals de marge, pagina, alinea of tabel. U kunt de juiste relatieve horizontale en verticale positieparameters kiezen om de gewenste plaatsing te bereiken.

#### Vraag: Is Aspose.Words voor .NET geschikt voor zowel desktop- als webapplicaties?

A: Ja, Aspose.Words voor .NET is een veelzijdige bibliotheek die geschikt is voor zowel desktop- als webapplicaties. Of u nu een Windows-applicatie of een webgebaseerd systeem bouwt, u kunt de bibliotheek moeiteloos integreren.
