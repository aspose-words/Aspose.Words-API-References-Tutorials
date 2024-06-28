---
title: Grenzen van de as in een grafiek
linktitle: Grenzen van de as in een grafiek
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de grenzen van een as in een diagram instelt met behulp van Aspose.Words voor .NET, waarmee u het bereik van waarden beheert die op de as worden weergegeven.
type: docs
weight: 10
url: /nl/net/programming-with-charts/bounds-of-axis/
---

In deze zelfstudie wordt uitgelegd hoe u de grenzen van een as in een diagram instelt met Aspose.Words voor .NET. Door een diagram in te voegen, seriegegevens toe te voegen en de asschaal te configureren, kunt u de minimum- en maximumwaarden voor de as definiëren.

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
 Maak een nieuw exemplaar van de`Document` klasse en een`DocumentBuilder` bezwaar maken tegen het werken met het document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Een diagram invoegen en configureren
 Voeg een diagram in het document in met behulp van de`InsertChart` werkwijze van de`DocumentBuilder` voorwerp. Stel het gewenste diagramtype en de afmetingen in.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Stap 4: Seriegegevens toevoegen
Wis eventuele bestaande reeksen in het diagram en voeg nieuwe reeksgegevens toe. In dit voorbeeld voegen we een serie toe met de labels 'Artikel 1' tot 'Artikel 5' en bijbehorende waarden.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Stap 5: Stel de grenzen van de as in
 Configureer de schaling van de Y-as door de minimum- en maximumwaarden in te stellen met behulp van de`Scaling.Minimum` En`Scaling.Maximum` eigenschappen van de as.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Stap 6: Sla het document op
 Sla het document op in de opgegeven map met behulp van de`Save` methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Voorbeeldbroncode voor Bounds Of Axis met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

Dat is het! U hebt met succes de grenzen van een as in een diagram ingesteld met Aspose.Words voor .NET.

## Conclusie
In deze zelfstudie hebt u geleerd hoe u de grenzen van een as in een diagram kunt instellen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen, kunt u een diagram invoegen en configureren, seriegegevens toevoegen en de minimum- en maximumwaarden voor de asschaling definiëren. Aspose.Words voor .NET biedt een krachtige en flexibele API voor woordenverwerking met Word-documenten, waarmee u eenvoudig dynamische en visueel aantrekkelijke grafieken kunt maken.


### Veelgestelde vragen

#### Q1. Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een bibliotheek waarmee ontwikkelaars programmatisch met Word-documenten kunnen werken. Het biedt een breed scala aan functies en functionaliteiten voor het maken, manipuleren en opslaan van Word-documenten.

#### Vraag 2. Hoe kan ik Aspose.Words voor .NET installeren?
Om Aspose.Words voor .NET te installeren, kunt u NuGet-pakketbeheer in Visual Studio gebruiken. Zoek eenvoudigweg naar "Apose.Words" in de NuGet-pakketbeheerder en installeer het in uw project.

#### Q3. Kan ik Aspose.Words voor .NET gebruiken met andere programmeertalen?
Nee, Aspose.Words voor .NET is specifiek ontworpen voor .NET-toepassingen. Het werkt met programmeertalen zoals C# en VB.NET.

#### Q4. Zijn er nog andere vereisten voor het gebruik van Aspose.Words voor .NET?
Naast het installeren van de Aspose.Words voor .NET-bibliotheek, moet u een basiskennis hebben van programmeren in C# en woordenverwerking met Word-documenten. Bekendheid met het .NET-framework zal ook nuttig zijn.
