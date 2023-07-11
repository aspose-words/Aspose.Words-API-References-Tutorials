---
title: Single Chart Series
linktitle: Single Chart Series
second_title: Aspose.Words Document Processing API
description: Learn how to customize single chart series in a chart using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-charts/single-chart-series/
---

This tutorial explains how to use Aspose.Words for .NET to customize single chart series in a chart. The provided source code demonstrates how to create a chart, access specific series, and modify their properties.

## Step 1: Set up the project

Ensure that you have the following prerequisites:

- Aspose.Words for .NET library installed. You can download it from the official Aspose website or use NuGet package manager to install it.
- A document directory path where the output document will be saved.

## Step 2: Create a new document and insert a chart

Create a new `Document` object and a `DocumentBuilder` to build the document.

```csharp
// Path to your document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Next, use the `InsertChart` method of the `DocumentBuilder` to insert a line chart into the document.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Step 3: Access and customize chart series

To modify single chart series, you need to access the `ChartSeries` objects of the chart.

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

## Step 4: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

This completes the implementation of customizing a single chart series using Aspose.Words for .NET.

### Example source code for Single Chart Series using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// You can also specify whether the line connecting the points on the chart shall be smoothed using Catmull-Rom splines.
	series0.Smooth = true;
	series1.Smooth = true;
	// Specifies whether by default the parent element shall inverts its colors if the value is negative.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```