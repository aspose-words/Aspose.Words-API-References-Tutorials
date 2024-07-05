---
title: Voeg een spreidingsdiagram in een Word-document in
linktitle: Voeg een spreidingsdiagram in een Word-document in
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een spreidingsdiagram in een document invoegt met Aspose.Words voor .NET. Voeg seriegegevens toe met X- en Y-coördinaten.
type: docs
weight: 10
url: /nl/net/programming-with-charts/insert-scatter-chart/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET gebruikt om een spreidingsdiagram in een document in te voegen. De meegeleverde broncode laat zien hoe u een diagram maakt, seriegegevens toevoegt en het document opslaat.

## Stap 1: Zet het project op

Zorg ervoor dat u aan de volgende vereisten voldoet:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd. U kunt het downloaden door NuGet-pakketbeheer te gebruiken om het te installeren.
- Een documentmappad waar het uitvoerdocument wordt opgeslagen.

## Stap 2: Maak een nieuw document en voeg een diagram in

 Maak een nieuwe`Document` voorwerp en een`DocumentBuilder` om het document op te bouwen.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Gebruik vervolgens de`InsertChart` werkwijze van de`DocumentBuilder` om een spreidingsdiagram in het document in te voegen.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Stap 3: Voeg seriegegevens toe aan het diagram

Voeg seriegegevens toe aan het diagram. In dit voorbeeld voegen we twee sets X- en Y-coördinaten toe.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Stap 4: Sla het document op

 Sla het document ten slotte op in de opgegeven map met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Hiermee is de implementatie van het invoegen van een spreidingsdiagram met Aspose.Words voor .NET voltooid.

### Voorbeeldbroncode voor het invoegen van een spreidingsdiagram met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u een spreidingsdiagram in een Word-document kunt invoegen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u een nieuw document maken, een spreidingsdiagram invoegen, reeksgegevens met X- en Y-coördinaten toevoegen en het document met het diagram opslaan.

Aspose.Words voor .NET biedt een uitgebreide API voor woordenverwerking met grafieken in Word-documenten. Spreidingsdiagrammen zijn handig voor het visualiseren en analyseren van gegevens met twee numerieke variabelen. Met Aspose.Words voor .NET kunt u eenvoudig spreidingsdiagrammen maken die de relatie tussen X- en Y-waarden weergeven en patronen of trends in de gegevens identificeren.

Door Aspose.Words voor .NET te gebruiken, kunt u het proces van het genereren van documenten met spreidingsdiagrammen automatiseren, waardoor u tijd en moeite bespaart bij het handmatig maken van documenten. De bibliotheek biedt een breed scala aan diagramtypen, waaronder spreidingsdiagrammen, en biedt verschillende aanpassingsopties om het uiterlijk van het diagram aan uw behoeften aan te passen.

### Veelgestelde vragen

#### Q1. Wat is een spreidingsdiagram?
Een spreidingsdiagram is een type diagram dat de relatie tussen twee numerieke variabelen weergeeft. Het bestaat uit een reeks punten die zijn uitgezet op een coördinatenraster, waarbij één variabele op de X-as wordt weergegeven en de andere variabele op de Y-as. Spreidingsdiagrammen worden gebruikt om patronen, correlaties of trends tussen twee sets gegevenspunten te identificeren.

#### Vraag 2. Kan ik meerdere reeksen aan het spreidingsdiagram toevoegen?
Ja, u kunt meerdere reeksen aan het spreidingsdiagram toevoegen met Aspose.Words voor .NET. Elke reeks vertegenwoordigt een reeks gegevenspunten met hun respectievelijke X- en Y-coördinaten. Door meerdere reeksen toe te voegen, kunt u verschillende gegevenssets binnen hetzelfde spreidingsdiagram vergelijken en analyseren, waardoor u een uitgebreid overzicht van uw gegevens krijgt.

#### Q3. Kan ik het uiterlijk van het spreidingsdiagram aanpassen?
Ja, met Aspose.Words voor .NET kunt u verschillende aspecten van het uiterlijk van het spreidingsdiagram aanpassen. U kunt eigenschappen wijzigen, zoals de kleur van de reeks, de vorm van de markering, de aslabels en de opmaak van het diagramgebied. De bibliotheek biedt een uitgebreide set API's om de visuele elementen van het diagram te beheren en een aangepast uiterlijk te creëren dat aan uw behoeften voldoet.

#### Q4. Kan ik het document met het ingevoegde spreidingsdiagram in verschillende formaten opslaan?
Ja, met Aspose.Words voor .NET kunt u het document met het ingevoegde spreidingsdiagram opslaan in verschillende formaten, zoals DOCX, PDF, HTML en meer. U kunt het gewenste uitvoerformaat kiezen op basis van uw vereisten en de`Save` werkwijze van de`Document` object om het document op te slaan. Het ingevoegde spreidingsdiagram blijft behouden in het opgeslagen document.

#### Vraag 5. Kan ik de gegevens en het uiterlijk van het spreidingsdiagram wijzigen nadat ik het heb ingevoegd?
Ja, nadat u het spreidingsdiagram in het document hebt ingevoegd, kunt u de gegevens en het uiterlijk ervan wijzigen met behulp van de API's van Aspose.Words voor .NET. U kunt de reeksgegevens bijwerken met nieuwe X- en Y-coördinaten, de vormen en kleuren van de markering wijzigen, aseigenschappen aanpassen en opmaakopties toepassen om dynamische en interactieve grafieken in uw Word-documenten te maken.