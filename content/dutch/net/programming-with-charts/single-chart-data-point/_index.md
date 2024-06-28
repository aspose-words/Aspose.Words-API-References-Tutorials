---
title: Pas één diagramgegevenspunt in een diagram aan
linktitle: Pas één diagramgegevenspunt in een diagram aan
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u één gegevenspunt in een diagram kunt aanpassen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-charts/single-chart-data-point/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET kunt gebruiken om één gegevenspunt in een diagram aan te passen. De meegeleverde broncode laat zien hoe u een diagram maakt, toegang krijgt tot specifieke gegevenspunten en hun eigenschappen wijzigt.

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

 Gebruik vervolgens de`InsertChart` werkwijze van de`DocumentBuilder` om een lijndiagram in het document in te voegen.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Stap 3: Gegevenspunten openen en aanpassen

 Om individuele gegevenspunten te wijzigen, moet u toegang krijgen tot de`ChartDataPointCollection` van de reeks en selecteer het gewenste gegevenspunt met behulp van de index.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## Stap 4: Sla het document op

 Sla het document ten slotte op in de opgegeven map met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

Hiermee is de implementatie voltooid van het aanpassen van een enkel gegevenspunt in een diagram met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor Single Chart Data Point met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u één gegevenspunt in een diagram kunt aanpassen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u een nieuw document maken, een lijndiagram invoegen, toegang krijgen tot specifieke gegevenspunten binnen de diagramserie en hun eigenschappen wijzigen om de gewenste aanpassing te bereiken.

Aspose.Words voor .NET biedt krachtige functies voor het manipuleren van diagrammen in Word-documenten. Door toegang te krijgen tot individuele gegevenspunten binnen een diagramreeks, kunt u specifieke wijzigingen aanbrengen om hun uiterlijk en gedrag aan te passen. Hiermee kunt u specifieke gegevenspunten markeren, markeringssymbolen wijzigen, markeringsgroottes aanpassen en meer, om de visuele weergave van uw diagram te verbeteren.

Door individuele gegevenspunten aan te passen, heeft u de flexibiliteit om belangrijke gegevens te benadrukken of specifieke trends in uw diagram te benadrukken. Met Aspose.Words voor .NET kunt u eenvoudig gegevenspunten in verschillende diagramtypen openen en wijzigen, zodat u visueel aantrekkelijke en informatieve diagrammen in uw Word-documenten kunt maken.

### Veelgestelde vragen

#### Q1. Kan ik meerdere gegevenspunten in een diagram aanpassen?
 Ja, u kunt meerdere gegevenspunten in een diagram aanpassen met Aspose.Words voor .NET. Door toegang te krijgen tot de`ChartDataPointCollection`van een reeks kunt u meerdere gegevenspunten selecteren en wijzigen op basis van hun indices. Gebruik een lus of individuele toewijzingen om de gewenste eigenschappen voor elk datapunt te wijzigen. Op deze manier kunt u verschillende aanpassingen toepassen op meerdere gegevenspunten binnen hetzelfde diagram.

#### Vraag 2. Hoe kan ik het markeringssymbool voor een datapunt wijzigen?
 Om het markeringssymbool voor een gegevenspunt in een diagram te wijzigen met Aspose.Words voor .NET, moet u naar het`Marker` eigendom van de`ChartDataPoint` bezwaar maken en instellen`Symbol` eigenschap naar het gewenste markeringssymbool. Markeringssymbolen vertegenwoordigen de vorm of het pictogram dat wordt gebruikt om elk gegevenspunt in het diagram weer te geven. U kunt kiezen uit een verscheidenheid aan ingebouwde markersymbolen, zoals cirkel, vierkant, ruit, driehoek, ster en meer.

#### Q3. Kan ik de grootte van een gegevenspuntmarkering aanpassen?
 Ja, u kunt de grootte van een gegevenspuntmarkering in een diagram aanpassen met Aspose.Words voor .NET. Toegang krijgen tot`Marker` eigendom van de`ChartDataPoint` bezwaar maken en instellen`Size`eigenschap aanpassen aan de gewenste markeringsgrootte. De grootte van de markering wordt doorgaans gespecificeerd in punten, waarbij een grotere waarde een grotere markeringsgrootte vertegenwoordigt. Door de grootte van de markering aan te passen, kunt u specifieke gegevenspunten benadrukken of deze onderscheiden op basis van hun betekenis.

#### Q4. Welke andere eigenschappen kan ik voor een datapunt wijzigen?
Aspose.Words voor .NET biedt een reeks eigenschappen die u voor een gegevenspunt in een diagram kunt wijzigen. Enkele van de vaak gewijzigde eigenschappen zijn onder meer het markeringssymbool, de markeringsgrootte, de markeringskleur, de zichtbaarheid van gegevenslabels, explosie, omkeren indien negatief, en meer. Met deze eigenschappen kunt u het uiterlijk, het gedrag en de interactiviteit van individuele gegevenspunten aanpassen, zodat u grafieken kunt maken die zijn afgestemd op uw specifieke vereisten.

#### Vraag 5. Kan ik gegevenspunten in andere diagramtypen aanpassen?
Ja, u kunt gegevenspunten in verschillende diagramtypen aanpassen met Aspose.Words voor .NET. Hoewel deze zelfstudie het aanpassen van gegevenspunten in een lijndiagram demonstreert, kunt u vergelijkbare technieken toepassen op andere diagramtypen, zoals kolomdiagrammen, staafdiagrammen, cirkeldiagrammen en meer. Het proces omvat toegang tot de reeksen en gegevenspunten in het diagram en het dienovereenkomstig aanpassen van hun eigenschappen.