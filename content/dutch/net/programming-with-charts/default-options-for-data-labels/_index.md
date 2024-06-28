---
title: Stel standaardopties in voor gegevenslabels in een diagram
linktitle: Stel standaardopties in voor gegevenslabels in een diagram
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u standaardopties voor gegevenslabels in een diagram instelt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-charts/default-options-for-data-labels/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET gebruikt om standaardopties voor gegevenslabels in een diagram in te stellen. De meegeleverde code laat zien hoe u een diagram maakt, gegevensreeksen toevoegt en de gegevenslabels aanpast met Aspose.Words.

## Stap 1: Zet het project op

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd. U kunt het downloaden met NuGet-pakketbeheer om het te installeren.
- Een documentmappad waar het uitvoerdocument wordt opgeslagen.

## Stap 2: Maak een nieuw document en voeg een diagram in.

 Laten we eerst een nieuwe maken`Document` voorwerp en een`DocumentBuilder` om het document op te bouwen.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Vervolgens voegen we een diagram in het document in met behulp van de`InsertChart` werkwijze van de`DocumentBuilder`. In dit voorbeeld voegen we een cirkeldiagram in.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Stap 3: Voeg gegevensreeksen toe aan het diagram

Laten we nu een gegevensreeks aan het diagram toevoegen. In dit voorbeeld voegen we drie categorieën en de bijbehorende waarden toe.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Stap 4: Pas gegevenslabels aan

 Om de gegevenslabels in het diagram aan te passen, hebben we toegang nodig tot het`ChartDataLabelCollection` object dat aan de serie is gekoppeld.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Vervolgens kunnen we verschillende eigenschappen van de`labels`object om de gewenste opties voor gegevenslabels in te stellen. In dit voorbeeld schakelen we het weergeven van het percentage en de waarde in, schakelen we aanhaallijnen uit en stellen we een aangepast scheidingsteken in.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Stap 5: Sla het document op

 Ten slotte slaan we het document op in de opgegeven map met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Hiermee is de implementatie voltooid van het instellen van standaardopties voor gegevenslabels in een diagram met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor standaardopties voor gegevenslabels met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u standaardopties voor gegevenslabels in een diagram kunt instellen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen, kunt u een diagram maken, gegevensreeksen toevoegen en de gegevenslabels aanpassen aan uw specifieke vereisten. Aspose.Words voor .NET biedt een krachtige API voor woordenverwerking met diagrammen in Word-documenten, waarmee u verschillende diagramelementen kunt manipuleren en het gewenste uiterlijk en de gewenste functionaliteit kunt bereiken.

 Door de eigenschappen van de`ChartDataLabelCollection`object dat aan de diagramserie is gekoppeld, kunt u de weergave van gegevenslabels beheren, inclusief opties zoals het weergeven van percentages, waarden, aanhaallijnen en aangepaste scheidingstekens. Dankzij deze flexibiliteit kunt u gegevens effectief presenteren en de visuele weergave van uw diagrammen verbeteren.

### Veelgestelde vragen

#### Q1. Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een bibliotheek waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, manipuleren en opslaan met behulp van .NET-toepassingen. Het biedt een breed scala aan functies voor tekstverwerking met documentelementen, waaronder grafieken.

#### Vraag 2. Hoe kan ik Aspose.Words voor .NET installeren?
U kunt Aspose.Words voor .NET installeren door het te downloaden met NuGet-pakketbeheer in Visual Studio. Zoek eenvoudigweg naar "Apose.Words" in de NuGet-pakketbeheerder en installeer het in uw project.

#### Q3. Kan ik andere aspecten van het diagram aanpassen met Aspose.Words voor .NET?
Ja, met Aspose.Words voor .NET kunt u verschillende aspecten van een diagram aanpassen, zoals diagramtype, aslabels, legenda, plotgebied en meer. U kunt verschillende eigenschappen van het diagramobject openen en wijzigen om het gewenste uiterlijk en gedrag te bereiken.

#### Q4. Kan ik het diagram in verschillende formaten opslaan?
 Ja, Aspose.Words voor .NET ondersteunt het opslaan van het document met het diagram in verschillende formaten, waaronder DOCX, PDF, HTML en meer. U kunt het juiste formaat kiezen op basis van uw vereisten en de`Save` werkwijze van de`Document` object om het document op te slaan.

#### Vraag 5. Kan ik deze technieken op andere diagramtypen toepassen?
Ja, de technieken die in deze zelfstudie worden beschreven, kunnen worden toegepast op andere diagramtypen die worden ondersteund door Aspose.Words voor .NET. De sleutel is om toegang te krijgen tot de relevante objecten en eigenschappen die specifiek zijn voor het diagramtype waarmee u woorden verwerkt.