---
title: Insert Scatter Chart in Word Document
linktitle: Insert Scatter Chart in Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to insert a scatter chart into a document using Aspose.Words for .NET. Add series data with X and Y coordinates.
type: docs
weight: 10
url: /net/programming-with-charts/insert-scatter-chart/
---

This tutorial explains how to use Aspose.Words for .NET to insert a scatter chart into a document. The provided source code demonstrates how to create a chart, add series data, and save the document.

## Step 1: Set up the project

Ensure that you have the following prerequisites:

- Aspose.Words for .NET library installed. You can download it by using NuGet package manager to install it.
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
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Step 3: Add series data to the chart

Add series data to the chart. In this example, we'll add two sets of X and Y coordinates.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Step 4: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

This completes the implementation of inserting a scatter chart using Aspose.Words for .NET.

### Example source code for Insert Scatter Chart using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Conclusion

In this tutorial, you have learned how to insert a scatter chart into a Word document using Aspose.Words for .NET. By following the step-by-step guide and using the provided source code, you can create a new document, insert a scatter chart, add series data with X and Y coordinates, and save the document with the chart.

Aspose.Words for .NET provides a comprehensive API for Words Processing with charts in Word documents. Scatter charts are useful for visualizing and analyzing data with two numerical variables. With Aspose.Words for .NET, you can easily create scatter charts that represent the relationship between X and Y values and identify patterns or trends in the data.

By using Aspose.Words for .NET, you can automate the process of generating documents with scatter charts, saving time and effort in manual document creation. The library offers a wide range of chart types, including scatter charts, and provides various customization options to tailor the appearance of the chart according to your needs.

### FAQs

#### Q1. What is a scatter chart?
A scatter chart is a type of chart that displays the relationship between two numerical variables. It consists of a series of points plotted on a coordinate grid, with one variable represented on the X-axis and the other variable represented on the Y-axis. Scatter charts are used to identify patterns, correlations, or trends between two sets of data points.

#### Q2. Can I add multiple series to the scatter chart?
Yes, you can add multiple series to the scatter chart using Aspose.Words for .NET. Each series represents a set of data points with their respective X and Y coordinates. By adding multiple series, you can compare and analyze different datasets within the same scatter chart, providing a comprehensive view of your data.

#### Q3. Can I customize the appearance of the scatter chart?
Yes, using Aspose.Words for .NET, you can customize various aspects of the scatter chart's appearance. You can modify properties such as series color, marker shape, axis labels, and chart area formatting. The library provides a rich set of APIs to control the visual elements of the chart and create a customized look that suits your needs.

#### Q4. Can I save the document with the inserted scatter chart in different formats?
Yes, Aspose.Words for .NET allows you to save the document with the inserted scatter chart in various formats, such as DOCX, PDF, HTML, and more. You can choose the desired output format based on your requirements and use the `Save` method of the `Document` object to save the document. The inserted scatter chart will be preserved in the saved document.

#### Q5. Can I modify the data and appearance of the scatter chart after inserting it?
Yes, after inserting the scatter chart into the document, you can modify its data and appearance using the APIs provided by Aspose.Words for .NET. You can update the series data with new X and Y coordinates, change the marker shapes and colors, customize axis properties, and apply formatting options to create dynamic and interactive charts in your Word documents.