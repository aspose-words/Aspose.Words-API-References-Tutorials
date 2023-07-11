---
title: Insert Area Chart
linktitle: Insert Area Chart
second_title: Aspose.Words Document Processing API
description: Learn how to insert an area chart into a document using Aspose.Words for .NET. Add series data and save the document with the chart.
type: docs
weight: 10
url: /net/programming-with-charts/insert-area-chart/
---

This tutorial explains how to use Aspose.Words for .NET to insert an area chart into a document. The provided source code demonstrates how to create a chart, add series data, and save the document.

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

Next, use the `InsertChart` method of the `DocumentBuilder` to insert an area chart into the document.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Step 3: Add series data to the chart

Add series data to the chart. In this example, we'll add five data points with corresponding dates and values.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## Step 4: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

This completes the implementation of inserting an area chart using Aspose.Words for .NET.

### Example source code for Insert Area Chart using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```