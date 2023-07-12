---
title: Insert Bubble Chart In Word Document
linktitle: Insert Bubble Chart In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to insert a bubble chart into a document using Aspose.Words for .NET. Add series data with X, Y, and bubble size values.
type: docs
weight: 10
url: /net/programming-with-charts/insert-bubble-chart/
---

This tutorial explains how to use Aspose.Words for .NET to insert a bubble chart into a document. The provided source code demonstrates how to create a chart, add series data, and save the document.

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

Next, use the `InsertChart` method of the `DocumentBuilder` to insert a bubble chart into the document.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## Step 3: Add series data to the chart

Add series data to the chart. In this example, we'll add three data points with corresponding X, Y, and bubble size values.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## Step 4: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

This completes the implementation of inserting a bubble chart using Aspose.Words for .NET.

### Example source code for Insert Bubble Chart using Aspose.Words for .NET 

```csharp
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

## Conclusion

In this tutorial, you have learned how to insert a bubble chart into a Word document using Aspose.Words for .NET. By following the step-by-step guide and using the provided source code, you can create a new document, insert a bubble chart, add series data, and save the document with the chart.

Aspose.Words for .NET provides a powerful API for working with charts in Word documents. Bubble charts are ideal for visualizing three-dimensional data, where each data point is represented by a bubble with X and Y coordinates and a size value. With Aspose.Words for .NET, you can create dynamic and informative bubble charts that enhance the visual representation of your data.

By using Aspose.Words for .NET, you can automate the process of generating documents with bubble charts, saving time and effort in manual document creation. The library offers a wide range of chart types and customization options, allowing you to create visually appealing and data-rich charts in your Word documents.

### FAQs

#### Q1. What is a bubble chart?
A bubble chart is a type of chart that displays three-dimensional data using bubbles or spheres. Each data point is represented by a bubble, where the X and Y coordinates determine the position of the bubble on the chart, and the size of the bubble represents the third dimension of the data. Bubble charts are useful for visualizing relationships and patterns among multiple variables.

#### Q2. Can I add multiple series to the bubble chart?
Yes, you can add multiple series to the bubble chart using Aspose.Words for .NET. Each series represents a set of data points with their respective X, Y, and bubble size values. By adding multiple series, you can compare and analyze different datasets within the same chart, providing a comprehensive view of your data.

#### Q3. Can I customize the appearance of the bubble chart?
Yes, using Aspose.Words for .NET, you can customize various aspects of the bubble chart's appearance. You can modify properties such as series color, bubble size, axis labels, and chart area formatting. The library provides a rich set of APIs to control the visual elements of the chart and create a customized look that suits your needs.

#### Q4. Can I save the document with the inserted bubble chart in different formats?
Yes, Aspose.Words for .NET allows you to save the document with the inserted bubble chart in various formats, such as DOCX, PDF, HTML, and more. You can choose the desired output format based on your requirements and use the `Save` method of the `Document` object to save the document. The inserted bubble chart will be preserved in the saved document.

#### Q5. Can I modify the data and appearance of the bubble chart after inserting it?
Yes, after inserting the bubble chart into the document, you can modify its data and appearance using the APIs provided by Aspose.Words for .NET. You can update the series data, change the bubble size, customize axis properties, and apply formatting options to create dynamic and interactive charts in your Word documents.