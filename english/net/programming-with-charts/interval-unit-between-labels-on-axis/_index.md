---
title: Interval Unit Between Labels On Axis
linktitle: Interval Unit Between Labels On Axis
second_title: Aspose.Words for .NET API Reference
description: Learn how to set the interval unit between labels on the axis of a chart using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-charts/interval-unit-between-labels-on-axis/
---

This tutorial explains how to use Aspose.Words for .NET to set the interval unit between labels on the axis of a chart. The provided source code demonstrates how to create a chart, add series data, and customize the axis labels.

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

Next, use the `InsertChart` method of the `DocumentBuilder` to insert a column chart into the document.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Step 3: Add series data to the chart

Add series data to the chart. In this example, we'll add five items with their corresponding values.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Step 4: Customize the axis labels

To set the interval unit between labels on the X-axis, access the `AxisX` property of the chart and set the `TickLabelSpacing` property to the desired value. In this example, we set the spacing to 2.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Step 5: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

This completes the implementation of setting the interval unit between labels on the axis using Aspose.Words for .NET.

### Example source code for Interval Unit Between Labels On Axis using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```