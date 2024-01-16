---
title: Pas het diagramgegevenslabel aan
linktitle: Pas het diagramgegevenslabel aan
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u gegevenslabels in een diagram kunt toevoegen en aanpassen met Aspose.Words voor .NET om aanvullende informatie over gegevenspunten te bieden.
type: docs
weight: 10
url: /nl/net/programming-with-charts/chart-data-label/
---

In deze zelfstudie wordt uitgelegd hoe u gegevenslabels in een diagram kunt toevoegen en aanpassen met Aspose.Words voor .NET. Gegevenslabels bieden aanvullende informatie over de gegevenspunten in een diagram.

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
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## Stap 4: Gegevenslabels aanpassen
Krijg toegang tot de verzameling gegevenslabels van de diagramserie en wijzig verschillende eigenschappen om het uiterlijk van de gegevenslabels aan te passen.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## Stap 5: Sla het document op
 Sla het document op in de opgegeven map met behulp van de`Save` methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithCharts.ChartDataLabel.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Voorbeeldbroncode voor diagramgegevenslabel met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// Wanneer u gegevenslabels toevoegt aan de gegevenspunten in een cirkeldiagram, worden er standaard aanhaallijnen weergegeven voor gegevenslabels die dat wel zijn
	// ver buiten het einde van de datapunten geplaatst. Aanhaallijnen creëren een visuele verbinding tussen een gegevenslabel en het bijbehorende label
	// bijbehorende datapunt.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

Dat is het! U hebt met succes gegevenslabels in een diagram toegevoegd en aangepast met Aspose.Words voor .NET.

## Conclusie
In deze zelfstudie hebt u geleerd hoe u gegevenslabels in een diagram kunt toevoegen en aanpassen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen, kunt u een diagram invoegen, toegang krijgen tot de verzameling gegevenslabels en de eigenschappen wijzigen om het uiterlijk van de gegevenslabels aan te passen. Aspose.Words voor .NET biedt een krachtige API voor woordenverwerking met Word-documenten en grafieken, waarmee u visueel aantrekkelijke en informatieve grafieken met aangepaste gegevenslabels kunt maken.

### Veelgestelde vragen

#### Q1. Wat zijn gegevenslabels in een diagram?
Gegevenslabels in een diagram bieden aanvullende informatie over de gegevenspunten die in het diagram worden weergegeven. Ze kunnen waarden, categorieën, serienamen, percentages of andere relevante details weergeven, afhankelijk van het diagramtype en de configuratie.

#### Vraag 2. Kan ik het uiterlijk van gegevenslabels aanpassen?
Ja, u kunt de weergave van gegevenslabels in een diagram aanpassen. Aspose.Words voor .NET biedt opties om verschillende eigenschappen van gegevenslabels te wijzigen, zoals het weergeven van legendasleutels, aanhaallijnen, categorienamen, reeksnamen, waarden en meer. U kunt ook scheidingstekens instellen en de labels opmaken zodat ze aan uw specifieke vereisten voldoen.

#### Q3. Kan ik gegevenslabels toevoegen aan elk diagramtype?
Ja, u kunt gegevenslabels toevoegen aan verschillende soorten diagrammen, waaronder staafdiagrammen, cirkeldiagrammen, lijndiagrammen en meer. Het proces voor het toevoegen en aanpassen van gegevenslabels kan enigszins variëren, afhankelijk van het diagramtype en de bibliotheek of tool die u gebruikt.
