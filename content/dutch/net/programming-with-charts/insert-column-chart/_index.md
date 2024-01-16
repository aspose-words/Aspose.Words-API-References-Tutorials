---
title: Kolomdiagram invoegen in een Word-document
linktitle: Kolomdiagram invoegen in een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een kolomdiagram in een document invoegt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-charts/insert-column-chart/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET gebruikt om een kolomdiagram in een document in te voegen. De meegeleverde broncode laat zien hoe u een diagram maakt, reeksgegevens toevoegt en het document opslaat.

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

 Gebruik vervolgens de`InsertChart` werkwijze van de`DocumentBuilder` om een kolomdiagram in het document in te voegen.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Stap 3: Voeg seriegegevens toe aan het diagram

Voeg seriegegevens toe aan het diagram. In dit voorbeeld voegen we twee categorieën en de bijbehorende waarden toe.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## Stap 4: Sla het document op

 Sla het document ten slotte op in de opgegeven map met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

Hiermee is de implementatie van het invoegen van een kolomdiagram met Aspose.Words voor .NET voltooid.

### Voorbeeldbroncode voor het invoegen van een kolomdiagram met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u een kolomdiagram in een Word-document kunt invoegen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u een nieuw document maken, een kolomdiagram invoegen, reeksgegevens toevoegen en het document met het diagram opslaan.

Aspose.Words voor .NET biedt een krachtige API voor woordenverwerking met grafieken in Word-documenten. Kolomdiagrammen worden vaak gebruikt om gegevens uit verschillende categorieën of groepen weer te geven en te vergelijken. Met Aspose.Words voor .NET kunt u eenvoudig kolomdiagrammen maken die uw gegevens effectief visualiseren en waardevolle inzichten bieden.

Door Aspose.Words voor .NET te gebruiken, kunt u het proces van het genereren van documenten met kolomdiagrammen automatiseren, waardoor u tijd en moeite bespaart bij het handmatig maken van documenten. De bibliotheek biedt een breed scala aan diagramtypen en aanpassingsopties, zodat u visueel aantrekkelijke en gegevensrijke diagrammen in uw Word-documenten kunt maken.

### Veelgestelde vragen

#### Q1. Wat is een kolomdiagram?
Een kolomdiagram is een type diagram dat gegevens in verticale staven of kolommen weergeeft. Elke kolom vertegenwoordigt doorgaans een categorie of groep, en de hoogte of lengte van de kolom geeft de waarde aan van de gegevens die aan die categorie zijn gekoppeld. Kolomdiagrammen worden vaak gebruikt om gegevens uit verschillende categorieën te vergelijken of om veranderingen in de loop van de tijd bij te houden.

#### Vraag 2. Kan ik meerdere reeksen aan het kolomdiagram toevoegen?
Ja, u kunt meerdere reeksen aan het kolomdiagram toevoegen met Aspose.Words voor .NET. Elke reeks vertegenwoordigt een reeks gegevenspunten met hun respectievelijke categorieën en waarden. Door meerdere reeksen toe te voegen, kunt u verschillende datasets binnen hetzelfde diagram vergelijken en analyseren, waardoor u een uitgebreid overzicht van uw gegevens krijgt.

#### Q3. Kan ik het uiterlijk van het kolomdiagram aanpassen?
Ja, met Aspose.Words voor .NET kunt u verschillende aspecten van het uiterlijk van het kolomdiagram aanpassen. U kunt eigenschappen wijzigen, zoals de kleur van de reeks, de aslabels, de kolombreedte en de opmaak van het diagramgebied. De bibliotheek biedt een uitgebreide set API's om de visuele elementen van het diagram te beheren en een aangepast uiterlijk te creëren dat aan uw behoeften voldoet.

#### Q4. Kan ik het document met het ingevoegde kolomdiagram in verschillende formaten opslaan?
 Ja, met Aspose.Words voor .NET kunt u het document met het ingevoegde kolomdiagram opslaan in verschillende formaten, zoals DOCX, PDF, HTML en meer. U kunt het gewenste uitvoerformaat kiezen op basis van uw vereisten en de`Save` werkwijze van de`Document` object om het document op te slaan. Het ingevoegde kolomdiagram blijft behouden in het opgeslagen document.

#### Vraag 5. Kan ik de gegevens en het uiterlijk van het kolomdiagram wijzigen nadat ik het heb ingevoegd?
Ja, nadat u het kolomdiagram in het document hebt ingevoegd, kunt u de gegevens en het uiterlijk ervan wijzigen met behulp van de API's van Aspose.Words voor .NET. U kunt de reeksgegevens bijwerken, de kolomkleuren wijzigen, aseigenschappen aanpassen en opmaakopties toepassen om dynamische en interactieve grafieken in uw Word-documenten te maken.