---
title: Bounds Of Axis
linktitle: Bounds Of Axis
second_title: Aspose.Words Document Processing API
description: Learn how to set the bounds of an axis in a chart using Aspose.Words for .NET controlling the range of values displayed on the axis.
type: docs
weight: 10
url: /net/programming-with-charts/bounds-of-axis/
---

This tutorial explains how to set the bounds of an axis in a chart using Aspose.Words for .NET. By inserting a chart, adding series data, and configuring the axis scaling, you can define the minimum and maximum values for the axis.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and working with Word documents.

## Step 1: Set up the Document Directory
Start by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where you want to save the document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Create a New Document and DocumentBuilder
Create a new instance of the `Document` class and a `DocumentBuilder` object to work with the document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 3: Insert and Configure a Chart
Insert a chart into the document using the `InsertChart` method of the `DocumentBuilder` object. Set the desired chart type and dimensions.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Step 4: Add Series Data
Clear any existing series in the chart and add new series data. In this example, we add a series with labels "Item 1" to "Item 5" and corresponding values.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Step 5: Set the Bounds of the Axis
Configure the scaling of the Y-axis by setting the minimum and maximum values using the `Scaling.Minimum` and `Scaling.Maximum` properties of the axis.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Step 6: Save the Document
Save the document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Example source code for Bounds Of Axis using Aspose.Words for .NET 

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
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

That's it! You have successfully set the bounds of an axis in a chart using Aspose.Words for .NET.
