---
title: Definieer XY-aseigenschappen in een diagram
linktitle: Definieer XY-aseigenschappen in een diagram
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u XY-aseigenschappen in een diagram definieert met Aspose.Words voor .NET. Aanpassingsopties voor de X- en Y-assen worden gedemonstreerd.
type: docs
weight: 10
url: /nl/net/programming-with-charts/define-xyaxis-properties/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET gebruikt om eigenschappen voor de X- en Y-assen in een diagram te definiëren. De meegeleverde broncode laat zien hoe u een diagram maakt, reeksgegevens toevoegt en de aseigenschappen aanpast.

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

 Voeg vervolgens een diagram in het document in met behulp van de`InsertChart` werkwijze van de`DocumentBuilder`. In dit voorbeeld voegen we een vlakdiagram in.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Stap 3: Voeg seriegegevens toe aan het diagram

Voeg seriegegevens toe aan het diagram. In dit voorbeeld voegen we vijf gegevenspunten toe met bijbehorende datums en waarden.

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

## Stap 4: Pas de eigenschappen van de X- en Y-as aan

 Om de eigenschappen van de X- en Y-assen aan te passen, gaat u naar de`ChartAxis` objecten die aan het diagram zijn gekoppeld.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Wijzig de eigenschappen van de`xAxis` En`yAxis`objecten om de gewenste opties voor de X- en Y-assen in te stellen. In dit voorbeeld demonstreren we enkele algemene eigenschappen die kunnen worden aangepast.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Stap 5: Sla het document op

 Sla het document ten slotte op in de opgegeven map met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

Hiermee is de implementatie voltooid van het definiëren van XY-aseigenschappen in een diagram met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor het definiëren van XYAxis-eigenschappen met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Grafiek invoegen
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// Wijzig de X-as in categorie in plaats van datum, zodat alle punten met gelijke intervallen op de X-as worden geplaatst.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //Gemeten in weergave-eenheden van de Y-as (honderden).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u eigenschappen voor de X- en Y-assen in een diagram definieert met behulp van Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen, kunt u een diagram maken, reeksgegevens toevoegen en de aseigenschappen aanpassen aan uw specifieke vereisten. Aspose.Words voor .NET biedt een uitgebreide API voor woordenverwerking met diagrammen in Word-documenten, waardoor u verschillende aspecten van het diagram kunt manipuleren, inclusief de assen.

Door toegang te krijgen tot de`ChartAxis` objecten die aan het diagram zijn gekoppeld, kunt u eigenschappen wijzigen, zoals het categorietype, askruisen, maatstreepjes, labelposities, schaling en meer. Dankzij deze flexibiliteit kunt u het uiterlijk en het gedrag van de diagramassen aanpassen, zodat uw gegevens effectief worden gepresenteerd.

Door Aspose.Words voor .NET te gebruiken, kunt u de mogelijkheden voor het maken en aanpassen van diagrammen naadloos integreren in uw .NET-toepassingen en het genereren van professioneel ogende documenten met rijke visualisaties automatiseren.

### Veelgestelde vragen

#### Q1. Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een krachtige bibliotheek voor documentverwerking waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, manipuleren en opslaan in .NET-toepassingen. Het biedt een breed scala aan functies voor tekstverwerking met documentelementen, waaronder grafieken.

#### Vraag 2. Hoe kan ik Aspose.Words voor .NET installeren?
kunt Aspose.Words voor .NET installeren door het te downloaden met behulp van NuGet-pakketbeheer in Visual Studio. Zoek eenvoudigweg naar "Apose.Words" in de NuGet-pakketbeheerder en installeer het in uw project.

#### Q3. Kan ik andere aspecten van het diagram aanpassen met Aspose.Words voor .NET?
Ja, Aspose.Words voor .NET biedt uitgebreide mogelijkheden voor het aanpassen van verschillende aspecten van een diagram. Naast het definiëren van aseigenschappen kunt u het diagramtype, gegevensreeksen, legenda, titel, plotgebied, gegevenslabels en vele andere elementen van het diagram wijzigen. De API biedt fijnmazige controle over het uiterlijk en gedrag van diagrammen.

#### Q4. Kan ik verschillende soorten diagrammen maken met Aspose.Words voor .NET?
 Ja, Aspose.Words voor .NET ondersteunt een breed scala aan diagramtypen, waaronder gebied, staaf, lijn, cirkel, spreiding en meer. U kunt gebruik maken van de`ChartType` opsomming om het gewenste diagramtype op te geven bij het invoegen van een diagramvorm in een Word-document.

#### Vraag 5. Kan ik het diagram in verschillende formaten opslaan?
Ja, met Aspose.Words voor .NET kunt u het document met het diagram in verschillende formaten opslaan, zoals DOCX, PDF, HTML en meer. U kunt het juiste formaat kiezen op basis van uw vereisten en de`Save` werkwijze van de`Document` object om het document op te slaan.

#### Vraag 6. Kan ik deze technieken toepassen op meerdere diagrammen in een document?
 Ja, u kunt deze technieken toepassen op meerdere diagrammen in een document door de noodzakelijke stappen voor elk diagram te herhalen. Je kunt aparte creëren`Chart` En`ChartAxis` objecten voor elk diagram en pas hun eigenschappen dienovereenkomstig aan. Aspose.Words voor .NET biedt volledige ondersteuning voor woordenverwerking met meerdere diagrammen in één document.