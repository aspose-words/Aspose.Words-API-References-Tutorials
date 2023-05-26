---
title: Diagramdataetikett
linktitle: Diagramdataetikett
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du lägger till och anpassar dataetiketter i ett diagram med Aspose.Words för .NET för att ge ytterligare information om datapunkter.
type: docs
weight: 10
url: /sv/net/programming-with-charts/chart-data-label/
---

Denna handledning förklarar hur du lägger till och anpassar dataetiketter i ett diagram med Aspose.Words för .NET. Dataetiketter ger ytterligare information om datapunkterna i ett diagram.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och att arbeta med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"`med den faktiska sökvägen till katalogen där du vill spara dokumentet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett nytt dokument och DocumentBuilder
 Skapa en ny instans av`Document` klass och a`DocumentBuilder` objekt för att arbeta med dokumentet.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Infoga och konfigurera ett diagram
 Infoga ett diagram i dokumentet med hjälp av`InsertChart` metod för`DocumentBuilder` objekt. Ställ in önskad diagramtyp och dimensioner.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## Steg 4: Anpassa dataetiketter
Gå till dataetikettsamlingen för diagramserien och ändra olika egenskaper för att anpassa utseendet på dataetiketterna.

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

## Steg 5: Spara dokumentet
 Spara dokumentet i den angivna katalogen med hjälp av`Save` metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithCharts.ChartDataLabel.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Exempel på källkod för diagramdataetikett med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	//Som standard, när du lägger till dataetiketter till datapunkterna i ett cirkeldiagram, visas ledarlinjer för dataetiketter som är
	// placerade långt utanför slutet av datapunkter. Ledarlinjer skapar en visuell koppling mellan en dataetikett och dess
	// motsvarande datapunkt.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

Det är allt! Du har framgångsrikt lagt till och anpassat dataetiketter i ett diagram med Aspose.Words för .NET.