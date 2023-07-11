---
title: Single Chart Data Point
linktitle: Single Chart Data Point
second_title: Aspose.Words Document Processing API
description: Learn how to customize a single data point in a chart using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-charts/single-chart-data-point/
---

This tutorial explains how to use Aspose.Words for .NET to customize a single data point in a chart. The provided source code demonstrates how to create a chart, access specific data points, and modify their properties.

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

## Step 3: Access and customize data points

To modify individual data points, you need to access the `ChartDataPointCollection` of the series and select the desired data point using the index.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## Step 4: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

This completes the implementation of customizing a single data point in a chart using Aspose.Words for .NET.

### Example source code for Single Chart Data Point using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```