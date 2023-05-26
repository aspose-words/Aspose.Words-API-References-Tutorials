---
title: Tick Multi Line Label Alignment
linktitle: Tick Multi Line Label Alignment
second_title: Aspose.Words for .NET API Reference
description: Learn how to align tick multi-line labels in a chart axis using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-charts/tick-multi-line-label-alignment/
---

This tutorial explains how to use Aspose.Words for .NET to set the alignment of tick multi-line labels in a chart axis. The provided source code demonstrates how to create a chart, access the axis, and modify the tick label alignment.

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

Next, use the `InsertChart` method of the `DocumentBuilder` to insert a scatter chart into the document.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Step 3: Set tick label alignment

To set the alignment of tick multi-line labels, access the `AxisX` property of the chart and set the `TickLabelAlignment` property to the desired alignment. In this example, we set the alignment to `ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Step 4: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

This completes the implementation of setting the tick multi-line label alignment using Aspose.Words for .NET.

### Example source code for Tick Multi Line Label Alignment using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// This property has effect only for multi-line labels.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```