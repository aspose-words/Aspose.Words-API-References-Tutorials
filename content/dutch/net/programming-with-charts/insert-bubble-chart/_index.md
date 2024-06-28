---
title: Voeg een bellendiagram in een Word-document in
linktitle: Voeg een bellendiagram in een Word-document in
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een bellendiagram in een document kunt invoegen met Aspose.Words voor .NET. Voeg reeksgegevens toe met waarden voor X, Y en belgrootte.
type: docs
weight: 10
url: /nl/net/programming-with-charts/insert-bubble-chart/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET gebruikt om een bellendiagram in een document in te voegen. De meegeleverde broncode laat zien hoe u een diagram maakt, seriegegevens toevoegt en het document opslaat.

## Stap 1: Zet het project op

Zorg ervoor dat u aan de volgende vereisten voldoet:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd. U kunt het downloaden door NuGet-pakketbeheer te gebruiken om het te installeren.
- Een documentmappad waar het uitvoerdocument wordt opgeslagen.

## Stap 2: Maak een nieuw document en voeg een diagram in.

 Maak een nieuwe`Document` voorwerp en een`DocumentBuilder` om het document op te bouwen.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Gebruik vervolgens de`InsertChart` werkwijze van de`DocumentBuilder` om een bellendiagram in het document in te voegen.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## Stap 3: Voeg seriegegevens toe aan het diagram

Voeg seriegegevens toe aan het diagram. In dit voorbeeld voegen we drie gegevenspunten toe met bijbehorende waarden voor X, Y en belgrootte.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## Stap 4: Sla het document op

 Sla het document ten slotte op in de opgegeven map met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

Hiermee is de implementatie van het invoegen van een bellendiagram met Aspose.Words voor .NET voltooid.

### Voorbeeldbroncode voor het invoegen van een bellendiagram met Aspose.Words voor .NET 

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u een bellendiagram in een Word-document kunt invoegen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u een nieuw document maken, een bellendiagram invoegen, seriegegevens toevoegen en het document met het diagram opslaan.

Aspose.Words voor .NET biedt een krachtige API voor woordenverwerking met grafieken in Word-documenten. Bellendiagrammen zijn ideaal voor het visualiseren van driedimensionale gegevens, waarbij elk gegevenspunt wordt weergegeven door een bel met X- en Y-coördinaten en een groottewaarde. Met Aspose.Words voor .NET kunt u dynamische en informatieve bellendiagrammen maken die de visuele weergave van uw gegevens verbeteren.

Door Aspose.Words voor .NET te gebruiken, kunt u het proces van het genereren van documenten met bellendiagrammen automatiseren, waardoor u tijd en moeite bespaart bij het handmatig maken van documenten. De bibliotheek biedt een breed scala aan diagramtypen en aanpassingsopties, zodat u visueel aantrekkelijke en gegevensrijke diagrammen in uw Word-documenten kunt maken.

### Veelgestelde vragen

#### Q1. Wat is een bellendiagram?
Een bellendiagram is een type diagram dat driedimensionale gegevens weergeeft met behulp van bellen of bollen. Elk gegevenspunt wordt weergegeven door een bel, waarbij de X- en Y-coördinaten de positie van de bel op de kaart bepalen, en de grootte van de bel de derde dimensie van de gegevens vertegenwoordigt. Bellendiagrammen zijn handig voor het visualiseren van relaties en patronen tussen meerdere variabelen.

#### Vraag 2. Kan ik meerdere reeksen aan het bellendiagram toevoegen?
Ja, u kunt meerdere reeksen aan het bellendiagram toevoegen met Aspose.Words voor .NET. Elke reeks vertegenwoordigt een reeks gegevenspunten met hun respectieve X-, Y- en belgroottewaarden. Door meerdere reeksen toe te voegen, kunt u verschillende datasets binnen hetzelfde diagram vergelijken en analyseren, waardoor u een uitgebreid overzicht van uw gegevens krijgt.

#### Q3. Kan ik het uiterlijk van het bellendiagram aanpassen?
Ja, met Aspose.Words voor .NET kunt u verschillende aspecten van het uiterlijk van het bellendiagram aanpassen. U kunt eigenschappen wijzigen, zoals de kleur van de reeks, de belgrootte, aslabels en de opmaak van het diagramgebied. De bibliotheek biedt een uitgebreide set API's om de visuele elementen van het diagram te beheren en een aangepast uiterlijk te creëren dat aan uw behoeften voldoet.

#### Q4. Kan ik het document met het ingevoegde bellendiagram in verschillende formaten opslaan?
 Ja, met Aspose.Words voor .NET kunt u het document met het ingevoegde bellendiagram opslaan in verschillende formaten, zoals DOCX, PDF, HTML en meer. U kunt het gewenste uitvoerformaat kiezen op basis van uw vereisten en de`Save` werkwijze van de`Document` object om het document op te slaan. Het ingevoegde bellendiagram blijft behouden in het opgeslagen document.

#### Vraag 5. Kan ik de gegevens en het uiterlijk van het bellendiagram wijzigen nadat ik het heb ingevoegd?
Ja, nadat u het bellendiagram in het document hebt ingevoegd, kunt u de gegevens en het uiterlijk ervan wijzigen met behulp van de API's van Aspose.Words voor .NET. U kunt de reeksgegevens bijwerken, de belgrootte wijzigen, aseigenschappen aanpassen en opmaakopties toepassen om dynamische en interactieve grafieken in uw Word-documenten te maken.