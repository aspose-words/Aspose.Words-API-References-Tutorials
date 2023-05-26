---
title: Single Chart Series
linktitle: Single Chart Series
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du anpassar enstaka diagramserier i ett diagram med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/single-chart-series/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att anpassa enstaka diagramserier i ett diagram. Den medföljande källkoden visar hur man skapar ett diagram, kommer åt specifika serier och ändrar deras egenskaper.

## Steg 1: Konfigurera projektet

Se till att du har följande förutsättningar:

- Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda NuGet-pakethanteraren för att installera den.
- En sökväg till dokumentkatalogen där utdatadokumentet kommer att sparas.

## Steg 2: Skapa ett nytt dokument och infoga ett diagram

 Skapa en ny`Document` föremål och ett`DocumentBuilder` att bygga dokumentet.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Använd sedan`InsertChart` metod för`DocumentBuilder` för att infoga ett linjediagram i dokumentet.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Steg 3: Få tillgång till och anpassa diagramserier

 För att ändra enstaka sjökortsserier måste du komma åt`ChartSeries` objekt i diagrammet.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Steg 4: Spara dokumentet

 Slutligen sparar du dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Detta slutför implementeringen av att anpassa en enda diagramserie med Aspose.Words för .NET.

### Exempel på källkod för Single Chart Series med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Du kan också ange om linjen som förbinder punkterna på diagrammet ska utjämnas med Catmull-Rom splines.
	series0.Smooth = true;
	series1.Smooth = true;
	// Anger om det överordnade elementet som standard ska invertera sina färger om värdet är negativt.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```