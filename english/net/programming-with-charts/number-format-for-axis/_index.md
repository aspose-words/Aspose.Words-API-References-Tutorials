---
title: Number Format For Axis
linktitle: Number Format For Axis
second_title: Aspose.Words for .NET API Reference
description: Learn how to set the number format for an axis in a chart using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-charts/number-format-for-axis/
---

This tutorial explains how to use Aspose.Words for .NET to set the number format for an axis in a chart. The provided source code demonstrates how to create a chart, add series data, and format the axis labels.

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
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Step 4: Format the axis labels

To set the number format for the Y-axis labels, access the `AxisY` property of the chart and set the `NumberFormat.FormatCode` property to the desired format. In this example, we set the format to "#,##0" to display numbers with thousands separators.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Step 5: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

This completes the implementation of setting the number format for the axis using Aspose.Words for .NET.

### Example source code for Number Format For Axis using Aspose.Words for .NET 

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
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```