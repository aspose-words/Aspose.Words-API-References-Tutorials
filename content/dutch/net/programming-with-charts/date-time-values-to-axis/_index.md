---
title: Voeg datum-tijdwaarden toe aan de as van een diagram
linktitle: Voeg datum-tijdwaarden toe aan de as van een diagram
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u datum-tijdwaarden aan de as van een diagram toevoegt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-charts/date-time-values-to-axis/
---

In deze zelfstudie wordt uitgelegd hoe u datum-tijdwaarden aan de as van een diagram kunt toevoegen met behulp van Aspose.Words voor .NET.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar u het document wilt opslaan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een nieuw document en DocumentBuilder
 Maak een nieuw exemplaar van de`Document` klasse en een`DocumentBuilder`bezwaar maken tegen het werken met het document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Een grafiekvorm invoegen en configureren
 Voeg een grafiekvorm in het document in met behulp van de`InsertChart` werkwijze van de`DocumentBuilder` voorwerp. Stel het gewenste diagramtype en de afmetingen in.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Stap 4: Voeg gegevens toe aan het diagram
Voeg gegevens toe aan de diagramserie, inclusief datum-tijdwaarden.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Stap 5: Configureer de as
Configureer de X-as van het diagram om de datum-tijdwaarden weer te geven.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Stap 6: Sla het document op
 Sla het document op in de opgegeven map met behulp van de`Save` methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithCharts.DateTimeValuesToAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Voorbeeldbroncode voor Date Time Values To Axis met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Stel grote eenheden in op een week en kleine eenheden op een dag.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Met deze voorbeeldcode wordt een nieuw Word-document gemaakt, wordt een kolomdiagram met datum-tijdwaarden op de X-as ingevoegd en wordt het document in de opgegeven map opgeslagen.

## Conclusie
In deze zelfstudie hebt u geleerd hoe u datum-tijdwaarden kunt toevoegen aan de as van een diagram met behulp van Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen, kunt u een diagram maken, datum-tijdwaarden aan de reeks toevoegen en de as configureren om de datum-tijdwaarden nauwkeurig weer te geven. Aspose.Words voor .NET biedt een krachtige reeks functies voor woordenverwerking met grafieken in Word-documenten, waardoor u gegevens effectief kunt weergeven en visualiseren met datum-tijdwaarden.

### Veelgestelde vragen

#### Q1. Kan ik datum-tijdwaarden toevoegen aan de as van een diagram met Aspose.Words voor .NET?
Ja, met Aspose.Words voor .NET kunt u datum-tijdwaarden toevoegen en weergeven op de as van een diagram in een Word-document. Aspose.Words biedt API's en functionaliteiten om met verschillende diagramtypen te werken en hun uiterlijk aan te passen, inclusief het verwerken van datum-tijdwaarden op de as.

#### Vraag 2. Hoe voeg ik datum-tijdwaarden toe aan de diagramserie?
 Als u datum-tijdwaarden aan de diagramserie wilt toevoegen, kunt u de`Add`methode van de serie van het diagram. Geef een matrix met datum-tijdwaarden op als categoriegegevens (X-as), samen met de bijbehorende reekswaarden. Hiermee kunt u gegevenspunten met datum-tijdwaarden in het diagram plotten.

#### Q3. Hoe kan ik de as configureren om datum-tijdwaarden weer te geven?
 U kunt de as van het diagram configureren om datum-tijdwaarden weer te geven door de juiste eigenschappen in te stellen. U kunt bijvoorbeeld de minimum- en maximumwaarden voor de as opgeven met behulp van de`Scaling.Minimum` En`Scaling.Maximum` eigenschappen, respectievelijk. Bovendien kunt u de hoofd- en secundaire eenheden instellen om het interval en de maatstreepjes voor de as te definiëren.
