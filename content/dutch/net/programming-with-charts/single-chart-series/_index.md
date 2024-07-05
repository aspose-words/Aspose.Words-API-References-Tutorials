---
title: Pas enkele grafiekreeksen in een grafiek aan
linktitle: Pas enkele grafiekreeksen in een grafiek aan
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u afzonderlijke diagramreeksen in een diagram kunt aanpassen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-charts/single-chart-series/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET kunt gebruiken om afzonderlijke diagramreeksen in een diagram aan te passen. De meegeleverde broncode laat zien hoe u een diagram maakt, toegang krijgt tot specifieke reeksen en hun eigenschappen wijzigt.

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

 Gebruik vervolgens de`InsertChart` werkwijze van de`DocumentBuilder` om een lijndiagram in het document in te voegen.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Stap 3: Kaartreeksen openen en aanpassen

 Om afzonderlijke kaartseries te wijzigen, heeft u toegang nodig tot het`ChartSeries` objecten van de kaart.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Stap 4: Sla het document op

 Sla het document ten slotte op in de opgegeven map met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Hiermee is de implementatie voltooid van het aanpassen van een enkele diagramserie met Aspose.Words voor .NET.

### Voorbeeldbroncode voor Single Chart Series met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// U kunt ook opgeven of de lijn die de punten op de kaart verbindt, moet worden afgevlakt met behulp van Catmull-Rom-splines.
	series0.Smooth = true;
	series1.Smooth = true;
	// Specificeert of het bovenliggende element standaard zijn kleuren moet omkeren als de waarde negatief is.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u een enkele grafiekreeks in een grafiek kunt aanpassen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u een nieuw document maken, een lijndiagram invoegen, toegang krijgen tot specifieke diagramreeksen en hun eigenschappen wijzigen om de gewenste aanpassing te bereiken.

Aspose.Words voor .NET biedt krachtige functies voor het manipuleren van diagrammen in Word-documenten. Door individuele kaartseries te openen, kunt u specifieke wijzigingen aanbrengen om het uiterlijk en gedrag ervan aan te passen. Hiermee kunt u de naam van de reeks wijzigen, de diagramlijn vloeiender maken, markeringen voor gegevenspunten aanpassen, kleuren voor negatieve waarden omkeren en meer, om de visuele weergave van uw diagram te verbeteren.

Door een enkele diagramreeks aan te passen, beschikt u over de flexibiliteit om specifieke gegevens te benadrukken of bepaalde trends in uw diagram te benadrukken. Met Aspose.Words voor .NET kunt u eenvoudig de eigenschappen van diagramreeksen openen en wijzigen, zodat u visueel aantrekkelijke en informatieve diagrammen in uw Word-documenten kunt maken.

### Veelgestelde vragen

#### Q1. Kan ik meerdere diagramseries in een diagram aanpassen?
 Ja, u kunt meerdere grafiekreeksen in een grafiek aanpassen met Aspose.Words voor .NET. Door toegang te krijgen tot de`ChartSeries`objecten in het diagram kunt u meerdere reeksen selecteren en wijzigen op basis van hun indexen of specifieke criteria. Gebruik een lus of individuele toewijzingen om de gewenste eigenschappen voor elke diagramserie te wijzigen. Op deze manier kunt u verschillende aanpassingen toepassen op meerdere series binnen hetzelfde diagram.

#### Vraag 2. Hoe kan ik de naam van een diagramserie wijzigen?
 Om de naam van een diagramreeks in een diagram te wijzigen met Aspose.Words voor .NET, moet u naar het`Name` eigendom van de`ChartSeries` object en stel het in op de gewenste naam. De serienaam wordt doorgaans weergegeven in de diagramlegenda of gegevenslabels, waardoor een beschrijvend label voor de serie wordt geboden. Door de serienaam te wijzigen, kunt u betekenisvolle namen opgeven die de gegevens weerspiegelen die door elke serie worden vertegenwoordigd.

#### Q3. Wat is het afvlakken van diagramreeksen?
Het vloeiend maken van diagramreeksen is een visuele verbeteringstechniek waarmee u een vloeiende lijn kunt maken die de punten op de kaart met elkaar verbindt. Het past een afvlakkingsalgoritme toe, zoals Catmull-Rom-splines, om tussen datapunten te interpoleren en een visueel aantrekkelijke curve te creëren. Als u het vloeiend maken van reeksen in een diagram wilt inschakelen met Aspose.Words voor .NET, gaat u naar de`Smooth` eigendom van de`ChartSeries` object en stel het in`true`. Vloeien kan handig zijn voor het weergeven van trends of patronen in gegevens met onregelmatige fluctuaties.

#### Q4. Hoe kan ik markeringen voor gegevenspunten in een diagramreeks aanpassen?
 Om markeringen voor gegevenspunten in een diagramserie aan te passen met Aspose.Words voor .NET, moet u toegang krijgen tot de`Marker` eigendom van de`ChartSeries` object en wijzig de eigenschappen ervan, zoals`Symbol` En`Size`. Markeringen zijn visuele indicatoren die op de grafiek worden geplaatst om individuele gegevenspunten weer te geven. U kunt kiezen uit een verscheidenheid aan ingebouwde markeringssymbolen en de grootte ervan aanpassen om specifieke gegevenspunten binnen de reeks te markeren of te onderscheiden.

#### Vraag 5. Kan ik kleuren voor negatieve waarden in een diagramserie omkeren?
 Ja, u kunt kleuren voor negatieve waarden in een diagramserie omkeren met Aspose.Words voor .NET. Door het instellen van de`InvertIfNegative` eigendom van de`ChartSeries` bezwaar tegen`true`, worden de kleuren voor gegevenspunten met negatieve waarden omgekeerd, waardoor ze visueel onderscheiden worden van positieve waarden. Deze functie kan handig zijn bij het vergelijken van positieve en negatieve waarden in een diagramserie, waardoor een duidelijk onderscheid tussen de twee wordt gemaakt.