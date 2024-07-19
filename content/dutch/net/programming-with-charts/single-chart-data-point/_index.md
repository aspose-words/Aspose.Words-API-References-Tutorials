---
title: Pas één diagramgegevenspunt in een diagram aan
linktitle: Pas één diagramgegevenspunt in een diagram aan
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u gegevenspunten van afzonderlijke diagrammen kunt aanpassen met Aspose.Words voor .NET in een gedetailleerde stapsgewijze handleiding. Verbeter uw diagrammen met unieke markeringen en formaten.
type: docs
weight: 10
url: /nl/net/programming-with-charts/single-chart-data-point/
---
## Invoering

Heeft u zich ooit afgevraagd hoe u uw grafieken kunt laten opvallen met unieke gegevenspunten? Nou, vandaag is je geluksdag! We duiken in het aanpassen van een enkel diagramgegevenspunt met Aspose.Words voor .NET. Maak je klaar voor een ritje door een stapsgewijze tutorial die niet alleen informatief is, maar ook leuk en gemakkelijk te volgen.

## Vereisten

Voordat we aan de slag gaan, zorgen we ervoor dat u over alle essentiële zaken beschikt:

-  Aspose.Words voor .NET Library: Zorg ervoor dat je de nieuwste versie hebt.[Download het hier](https://releases.aspose.com/words/net/).
- .NET Framework: Zorg ervoor dat .NET Framework op uw computer is geïnstalleerd.
- Basiskennis van C#: Een basiskennis van programmeren in C# zal nuttig zijn.
- Geïntegreerde ontwikkelomgeving (IDE): Visual Studio wordt aanbevolen.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren om de bal aan het rollen te krijgen:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Stap 1: Initialiseer het document en DocumentBuilder

Oké, laten we beginnen met het initialiseren van een nieuw document en een DocumentBuilder. Dit zal het canvas zijn voor onze kaart.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Hier,`dataDir` is het mappad waar u uw document opslaat. De`DocumentBuilder` class helpt bij het construeren van het document.

## Stap 2: Voeg een diagram in

Laten we vervolgens een lijndiagram in het document invoegen. Dit wordt onze speeltuin voor het aanpassen van datapunten.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

 De`InsertChart` methode neemt het diagramtype, de breedte en de hoogte als parameters. In dit geval voegen we een lijndiagram in met een breedte van 432 en een hoogte van 252.

## Stap 3: Toegang tot kaartseries

Nu is het tijd om toegang te krijgen tot de series in onze grafiek. Een diagram kan meerdere reeksen bevatten, en elke reeks bevat gegevenspunten.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];
```

Hier hebben we toegang tot de eerste twee series in onze grafiek. 

## Stap 4: Gegevenspunten aanpassen

Hier gebeurt de magie! Laten we specifieke gegevenspunten binnen onze reeks aanpassen.

```csharp
ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];
```

We halen de gegevenspunten uit de eerste reeks op. Laten we nu deze punten aanpassen.

### Pas gegevenspunt 00 aan

```csharp
dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;
```

 Voor`dataPoint00`, stellen we een explosie in (handig voor cirkeldiagrammen), veranderen we het markeringssymbool in een cirkel en stellen we de markeringsgrootte in op 15.

### Pas gegevenspunt 01 aan

```csharp
dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;
```

 Voor`dataPoint01`, veranderen we het markeringssymbool in een diamant en stellen we de markeringsgrootte in op 20.

### Pas gegevenspunt in serie 1 aan

```csharp
ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

 Voor het derde gegevenspunt in`series1`, we stellen het in op omkeren als de waarde negatief is, veranderen het markeringssymbool in een ster en stellen de markeringsgrootte in op 20.

## Stap 5: Sla het document op

Laten we tot slot ons document met alle aanpassingen opslaan.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

 Deze regel slaat het document op in de door u opgegeven map met de naam`WorkingWithCharts.SingleChartDataPoint.docx`.

## Conclusie

En daar heb je het! U hebt met succes individuele gegevenspunten in een diagram aangepast met Aspose.Words voor .NET. Door een paar eigenschappen aan te passen, kunt u uw diagrammen veel informatiever en visueel aantrekkelijker maken. Experimenteer dus met verschillende markeringen en formaten om te zien wat het beste werkt voor uw gegevens.

## Veelgestelde vragen

### Kan ik gegevenspunten in andere typen diagrammen aanpassen?

Absoluut! U kunt gegevenspunten in verschillende diagramtypen aanpassen, waaronder staafdiagrammen, cirkeldiagrammen en meer. Het proces is vergelijkbaar voor verschillende diagramtypen.

### Is het mogelijk om aangepaste labels aan datapunten toe te voegen?

 Ja, u kunt aangepaste labels toevoegen aan gegevenspunten met behulp van de`ChartDataPoint.Label` eigendom. Hierdoor kunt u voor elk gegevenspunt meer context bieden.

### Hoe kan ik een datapunt uit een reeks verwijderen?

 U kunt een gegevenspunt verwijderen door de zichtbaarheid ervan in te stellen op false met`dataPoint.IsVisible = false`.

### Kan ik afbeeldingen gebruiken als markeringen voor gegevenspunten?

Hoewel Aspose.Words het gebruik van afbeeldingen niet rechtstreeks als markeringen ondersteunt, kunt u aangepaste vormen maken en deze als markeringen gebruiken.

### Is het mogelijk om gegevenspunten in het diagram te animeren?

Aspose.Words voor .NET ondersteunt geen animatie voor diagramgegevenspunten. U kunt echter met andere hulpmiddelen geanimeerde diagrammen maken en deze in uw Word-documenten insluiten.