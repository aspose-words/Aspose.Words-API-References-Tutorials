---
title: Grafiek maken en aanpassen met behulp van vorm
linktitle: Grafiek maken en aanpassen met behulp van vorm
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een diagram kunt maken en aanpassen met behulp van een vorm in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-charts/create-chart-using-shape/
---

In deze zelfstudie wordt uitgelegd hoe u een diagram maakt met behulp van een vorm in een Word-document met Aspose.Words voor .NET.

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

## Stap 3: Een grafiekvorm invoegen en configureren
 Voeg een grafiekvorm in het document in met behulp van de`InsertChart` werkwijze van de`DocumentBuilder` voorwerp. Stel het gewenste diagramtype en de afmetingen in.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Stap 4: Pas de grafiek aan
Pas het diagram aan door verschillende eigenschappen te wijzigen, zoals de diagramtitel en legenda.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Stap 5: Bewaar het document
 Sla het document op in de opgegeven map met behulp van de`Save` methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Voorbeeldbroncode voor het maken van een diagram met behulp van Shape met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Houd er rekening mee dat als een nul- of lege waarde wordt opgegeven als titeltekst, de automatisch gegenereerde titel wordt weergegeven.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

Dat is het! U hebt met succes een diagram gemaakt met behulp van een vorm in een Word-document met Aspose.Words voor .NET.

## Conclusie
In deze zelfstudie hebt u geleerd hoe u een diagram kunt maken met behulp van een vorm in een Word-document met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen, kunt u een diagramvorm invoegen en configureren, het uiterlijk ervan aanpassen en het document opslaan. Aspose.Words voor .NET biedt een uitgebreide reeks functies voor woordenverwerking met Word-documenten en grafieken, waardoor u professioneel ogende en visueel aantrekkelijke grafieken rechtstreeks in uw .NET-toepassingen kunt maken.

### Veelgestelde vragen

#### Q1. Kan ik diagrammen maken in een Word-document met Aspose.Words voor .NET?
Ja, met Aspose.Words voor .NET kunt u programmatisch diagrammen in een Word-document maken. Aspose.Words biedt API's en functionaliteiten om verschillende soorten diagrammen in te voegen, het uiterlijk ervan aan te passen en diagramgegevens te manipuleren.

#### Vraag 2. Welke grafiektypen worden ondersteund door Aspose.Words voor .NET?
Aspose.Words voor .NET ondersteunt een breed scala aan diagramtypen, waaronder lijndiagrammen, staafdiagrammen, cirkeldiagrammen, vlakdiagrammen, spreidingsdiagrammen en meer. U kunt het juiste diagramtype kiezen op basis van uw gegevens- en visualisatievereisten.

#### Q3. Kan ik het uiterlijk van het gemaakte diagram aanpassen?
Ja, u kunt het uiterlijk van het gemaakte diagram aanpassen met Aspose.Words voor .NET. U kunt eigenschappen zoals diagramtitel, legendapositie, gegevenslabels, aslabels, kleuren en andere visuele elementen wijzigen om aan uw specifieke ontwerp- en opmaakbehoeften te voldoen.
