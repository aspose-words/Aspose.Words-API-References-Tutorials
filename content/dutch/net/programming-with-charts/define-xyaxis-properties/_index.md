---
title: Definieer XY-aseigenschappen in een diagram
linktitle: Definieer XY-aseigenschappen in een diagram
second_title: Aspose.Words-API voor documentverwerking
description: Leer met deze stapsgewijze handleiding hoe u XY-aseigenschappen in een diagram definieert met Aspose.Words voor .NET. Perfect voor .NET-ontwikkelaars.
type: docs
weight: 10
url: /nl/net/programming-with-charts/define-xyaxis-properties/
---
## Invoering

Grafieken zijn een krachtig hulpmiddel voor het visualiseren van gegevens. Wanneer u professionele documenten met dynamische grafieken moet maken, is Aspose.Words voor .NET een bibliotheek van onschatbare waarde. Dit artikel leidt u door het proces van het definiëren van XY-aseigenschappen in een diagram met behulp van Aspose.Words voor .NET, waarbij elke stap wordt opgesplitst om duidelijkheid en begrijpelijkheid te garanderen.

## Vereisten

Voordat je in de codering duikt, zijn er een paar vereisten die je moet hebben:

1. Aspose.Words voor .NET: Zorg ervoor dat u over de Aspose.Words voor .NET-bibliotheek beschikt. Jij kan[download het hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: u hebt een geïntegreerde ontwikkelomgeving (IDE) zoals Visual Studio nodig.
3. .NET Framework: Zorg ervoor dat uw ontwikkelomgeving is ingesteld voor .NET-ontwikkeling.
4. Basiskennis van C#: Deze handleiding gaat ervan uit dat u een basiskennis hebt van programmeren in C#.

## Naamruimten importeren

Om te beginnen moet u de benodigde naamruimten in uw project importeren. Dit zorgt ervoor dat u toegang heeft tot alle klassen en methoden die nodig zijn voor het maken en manipuleren van documenten en grafieken.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

We zullen het proces opsplitsen in eenvoudige stappen, waarbij elke stap zich richt op een specifiek onderdeel van het definiëren van de XY-aseigenschappen in een diagram.

## Stap 1: Initialiseer het document en DocumentBuilder

 Eerst moet u een nieuw document initialiseren en een`DocumentBuilder` voorwerp. De`DocumentBuilder` helpt bij het invoegen van inhoud in het document.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Voeg een diagram in

Vervolgens voegt u een diagram in het document in. In dit voorbeeld gebruiken we een vlakdiagram. U kunt de afmetingen van het diagram indien nodig aanpassen.

```csharp
// Grafiek invoegen
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Stap 3: Wis de standaardreeks en voeg aangepaste gegevens toe

Standaard heeft het diagram een aantal vooraf gedefinieerde reeksen. We zullen deze wissen en onze aangepaste gegevensreeksen toevoegen.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
	new DateTime[]
	{
		new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
		new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
	},
	new double[] { 640, 320, 280, 120, 150 });
```

## Stap 4: Definieer de X-aseigenschappen

Nu is het tijd om de eigenschappen voor de X-as te definiëren. Dit omvat het instellen van het categorietype, het aanpassen van de kruising van de assen en het aanpassen van maatstreepjes en labels.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3; //Gemeten in weergave-eenheden van de Y-as (honderden).
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;
```

## Stap 5: Definieer de Y-aseigenschappen

Op dezelfde manier stelt u de eigenschappen voor de Y-as in. Dit omvat het instellen van de positie van het vinkje, de grote en kleine eenheden, de weergave-eenheid en de schaalverdeling.

```csharp
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Stap 6: Sla het document op

Sla het document ten slotte op in de door u opgegeven map. Hierdoor wordt het Word-document met het aangepaste diagram gegenereerd.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Conclusie

Het maken en aanpassen van grafieken in Word-documenten met Aspose.Words voor .NET is eenvoudig als u eenmaal de stappen begrijpt. Deze gids heeft u door het proces geleid van het definiëren van XY-aseigenschappen in een diagram, vanaf het initialiseren van het document tot het opslaan van het eindproduct. Met deze vaardigheden kunt u gedetailleerde, professioneel ogende grafieken maken die uw documenten verrijken.

## Veelgestelde vragen

### Welke soorten diagrammen kan ik maken met Aspose.Words voor .NET?
U kunt verschillende soorten diagrammen maken, waaronder vlak-, staaf-, lijn-, cirkeldiagrammen en meer.

### Hoe installeer ik Aspose.Words voor .NET?
 U kunt Aspose.Words voor .NET downloaden van[hier](https://releases.aspose.com/words/net/) en volg de meegeleverde installatie-instructies.

### Kan ik het uiterlijk van mijn diagrammen aanpassen?
Ja, Aspose.Words voor .NET maakt uitgebreide aanpassingen van grafieken mogelijk, inclusief kleuren, lettertypen en aseigenschappen.

### Is er een gratis proefversie beschikbaar voor Aspose.Words voor .NET?
 Ja, u kunt een gratis proefperiode krijgen[hier](https://releases.aspose.com/).

### Waar kan ik meer tutorials en documentatie vinden?
 Meer tutorials en gedetailleerde documentatie vindt u op de[Aspose.Words voor .NET-documentatiepagina](https://reference.aspose.com/words/net/).
