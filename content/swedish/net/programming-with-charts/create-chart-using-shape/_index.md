---
title: Skapa och anpassa diagram med Shape
linktitle: Skapa och anpassa diagram med Shape
second_title: Aspose.Words Document Processing API
description: Lär dig hur du skapar och anpassar ett diagram med hjälp av en form i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/create-chart-using-shape/
---

Denna handledning förklarar hur man skapar ett diagram med hjälp av en form i ett Word-dokument med Aspose.Words för .NET.

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
 Skapa en ny instans av`Document` klass och a`DocumentBuilder`objekt för att arbeta med dokumentet.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Infoga och konfigurera en diagramform
 Infoga en diagramform i dokumentet med hjälp av`InsertChart` metod för`DocumentBuilder` objekt. Ställ in önskad diagramtyp och dimensioner.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Steg 4: Anpassa diagrammet
Anpassa diagrammet genom att modifiera olika egenskaper som diagrammets titel och förklaring.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Steg 5: Spara dokumentet
 Spara dokumentet i den angivna katalogen med hjälp av`Save` metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Exempel på källkod för Skapa diagram med Shape med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Observera att om null eller tomt värde anges som titeltext, kommer automatiskt genererad titel att visas.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

Det är allt! Du har framgångsrikt skapat ett diagram med hjälp av en form i ett Word-dokument med Aspose.Words för .NET.

## Slutsats
den här handledningen har du lärt dig hur du skapar ett diagram med hjälp av en form i ett Word-dokument med Aspose.Words för .NET. Genom att följa steg-för-steg-guiden kan du infoga och konfigurera en diagramform, anpassa dess utseende och spara dokumentet. Aspose.Words för .NET tillhandahåller en omfattande uppsättning funktioner för ordbehandling med Word-dokument och diagram, vilket gör att du kan skapa professionella och visuellt tilltalande diagram direkt i dina .NET-applikationer.

### Vanliga frågor

#### Q1. Kan jag skapa diagram i ett Word-dokument med Aspose.Words för .NET?
Ja, med Aspose.Words för .NET kan du skapa diagram i ett Word-dokument programmatiskt. Aspose.Words tillhandahåller API:er och funktioner för att infoga olika typer av diagram, anpassa deras utseende och manipulera diagramdata.

#### Q2. Vilka diagramtyper stöds av Aspose.Words för .NET?
Aspose.Words för .NET stöder ett brett utbud av diagramtyper, inklusive linjediagram, stapeldiagram, cirkeldiagram, områdesdiagram, punktdiagram och mer. Du kan välja lämplig diagramtyp baserat på dina data- och visualiseringskrav.

#### Q3. Kan jag anpassa utseendet på det skapade diagrammet?
Ja, du kan anpassa utseendet på det skapade diagrammet med Aspose.Words för .NET. Du kan ändra egenskaper som diagramtitel, förklaringsposition, dataetiketter, axeletiketter, färger och andra visuella element för att möta dina specifika design- och formateringsbehov.
