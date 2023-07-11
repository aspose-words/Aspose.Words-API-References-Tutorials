---
title: Hide Chart Axis
linktitle: Hide Chart Axis
second_title: Aspose.Words Document Processing API
description: Learn how to hide the chart axis in a document using Aspose.Words for .NET. Hide the axis for a cleaner and more focused chart display.
type: docs
weight: 10
url: /net/programming-with-charts/hide-chart-axis/
---

This tutorial explains how to use Aspose.Words for .NET to hide the chart axis in a document. The provided source code demonstrates how to create a chart, add series data, and hide the chart axis.

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

Next, insert a chart into the document using the `InsertChart` method of the `DocumentBuilder`. In this example, we'll insert a column chart.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Step 3: Add series data to the chart

Add series data to the chart. In this example, we'll add five items and their corresponding values.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Step 4: Hide the chart axis

To hide the chart axis, access the `AxisY` property of the chart and set the `Hidden` property to `true`.

```csharp
chart.AxisY.Hidden = true;
```

In this example, we hide the Y-axis of the chart.

## Step 5: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

This completes the implementation of hiding the chart axis using Aspose.Words for .NET.

### Example source code for Hide Chart Axis using Aspose.Words for .NET 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```