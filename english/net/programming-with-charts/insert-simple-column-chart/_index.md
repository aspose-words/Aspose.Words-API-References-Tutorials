---
title: Insert Simple Column Chart In A Word Document
linktitle: Insert Simple Column Chart In A Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to insert a simple column chart into a document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-charts/insert-simple-column-chart/
---

This tutorial explains how to use Aspose.Words for .NET to insert a simple column chart into a document. The provided source code demonstrates how to create a chart, add series data, and save the document.

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

Next, use the `InsertChart` method of the `DocumentBuilder` to insert a column chart into the document. You can specify different chart types and sizes as per your requirements.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Step 3: Add series data to the chart

Add series data to the chart. In this example, we'll add multiple series with two categories each.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## Step 4: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

This completes the implementation of inserting a simple column chart using Aspose.Words for .NET.

### Example source code for Insert Simple Column Chart using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// You can specify different chart types and sizes.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Delete default generated series.
	seriesColl.Clear();
	// Create category names array, in this tutorial we have two categories.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Please note, data arrays must not be empty and arrays must be the same size.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Conclusion

In this tutorial, you have learned how to insert a simple column chart into a Word document using Aspose.Words for .NET. By following the step-by-step guide and using the provided source code, you can create a new document, insert a column chart, add multiple series with categories and corresponding values, and save the document with the chart.

Aspose.Words for .NET provides a powerful and flexible API for Words Processing with charts in Word documents. The simple column chart is an effective way to represent and compare data in different categories. With Aspose.Words for .NET, you can easily create column charts with custom data, add multiple series for visual comparison, and customize the appearance of the chart according to your requirements.

By using Aspose.Words for .NET, you can automate the process of generating documents with column charts, saving time and effort in manual document creation. The library offers a wide range of chart types, including simple column charts, and provides various customization options to tailor the appearance of the chart to suit your needs.

### FAQs

#### Q1. What is a column chart?
A column chart is a type of chart that displays data using vertical bars of varying heights. Each column represents a category, and the height of the column corresponds to the value of that category. Column charts are commonly used to compare data across different categories or to track changes over time.

#### Q2. Can I add multiple series to the column chart?
Yes, using Aspose.Words for .NET, you can add multiple series to the column chart. Each series represents a set of data points with their respective categories and values. By adding multiple series, you can compare and analyze different datasets within the same column chart, providing a comprehensive view of your data.

#### Q3. Can I customize the appearance of the column chart?
Yes, Aspose.Words for .NET allows you to customize various aspects of the column chart's appearance. You can modify properties such as series color, axis labels, data labels, and chart area formatting. The library provides a rich set of APIs to control the visual elements of the chart and create a customized look that suits your needs.

#### Q4. Can I save the document with the inserted column chart in different formats?
Yes, Aspose.Words for .NET allows you to save the document with the inserted column chart in various formats, such as DOCX, PDF, HTML, and more. You can choose the desired output format based on your requirements and use the `Save` method of the `Document` object to save the document. The inserted column chart will be preserved in the saved document.

#### Q5. Can I modify the data and appearance of the column chart after inserting it?
Yes, after inserting the column chart into the document, you can modify its data and appearance using the APIs provided by Aspose.Words for .NET. You can update the series data with new categories and values, change the colors and formatting of the columns, customize axis properties, and apply various formatting options to create dynamic and visually appealing charts in your Word documents.