---
title: Lägg till datum och tid värden till axeln i ett diagram
linktitle: Lägg till datum och tid värden till axeln i ett diagram
second_title: Aspose.Words Document Processing API
description: Lär dig hur du lägger till datum och tid värden till axeln i ett diagram med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/date-time-values-to-axis/
---

Denna handledning förklarar hur du lägger till datum och tid värden till axeln i ett diagram med Aspose.Words för .NET.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och ordbehandling med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till katalogen där du vill spara dokumentet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett nytt dokument och DocumentBuilder
 Skapa en ny instans av`Document` klass och a`DocumentBuilder` objekt för att arbeta med dokumentet.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Infoga och konfigurera en diagramform
 Infoga en diagramform i dokumentet med hjälp av`InsertChart` metod för`DocumentBuilder` objekt. Ställ in önskad diagramtyp och dimensioner.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Steg 4: Lägg till data i diagrammet
Lägg till data till diagramserien, inklusive datum och tidsvärden.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Steg 5: Konfigurera Axis
Konfigurera X-axeln för diagrammet för att visa datum och tid.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Steg 6: Spara dokumentet
 Spara dokumentet i den angivna katalogen med hjälp av`Save` metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithCharts.DateTimeValuesToAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Exempel på källkod för Date Time Values To Axis med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
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
	// Ställ in större enheter till en vecka och mindre enheter till en dag.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Den här exempelkoden skapar ett nytt Word-dokument, infogar ett kolumndiagram med datum och tidsvärden på X-axeln och sparar dokumentet i den angivna katalogen.

## Slutsats
den här handledningen har du lärt dig hur du lägger till datum och tid värden till axeln i ett diagram med Aspose.Words för .NET. Genom att följa den steg-för-steg-guiden kan du skapa ett diagram, lägga till datum och tid värden till serien och konfigurera axeln för att visa datum och tid värden korrekt. Aspose.Words för .NET tillhandahåller en kraftfull uppsättning funktioner för ordbehandling med diagram i Word-dokument, så att du kan representera och visualisera data med datum och tid värden effektivt.

### Vanliga frågor

#### Q1. Kan jag lägga till datum och tid värden till axeln i ett diagram med Aspose.Words för .NET?
Ja, med Aspose.Words för .NET kan du lägga till och visa datum och tid värden på axeln av ett diagram i ett Word-dokument. Aspose.Words tillhandahåller API:er och funktioner för att arbeta med olika diagramtyper och anpassa deras utseende, inklusive hantering av datum och tidsvärden på axeln.

#### Q2. Hur lägger jag till datum och tid värden till diagramserien?
 För att lägga till datum och tid värden till diagramserien kan du använda`Add`metoden för diagrammets serie. Ange en matris av datum och tid värden som kategoridata (X-axel) tillsammans med motsvarande serievärden. Detta låter dig plotta datapunkter med datum och tidsvärden i diagrammet.

#### Q3. Hur kan jag konfigurera axeln för att visa datum och tid?
 Du kan konfigurera diagrammets axel för att visa datum och tid genom att ställa in lämpliga egenskaper. Till exempel kan du ange lägsta och högsta värden för axeln med hjälp av`Scaling.Minimum` och`Scaling.Maximum` respektive fastigheter. Dessutom kan du ställa in de stora och små enheterna för att definiera intervall och bockmarkeringar för axeln.
