---
title: Insert Area Chart Into A Word Document
linktitle: Insert Area Chart Into A Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to insert an area chart into a document using Aspose.Words for .NET. Add series data and save the document with the chart.
type: docs
weight: 10
url: /net/programming-with-charts/insert-area-chart/
---

This tutorial explains how to use Aspose.Words for .NET to insert an area chart into a document. The provided source code demonstrates how to create a chart, add series data, and save the document.

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

### Conclusion

In this tutorial, you have learned how to insert an area chart into a Word document using Aspose.Words for .NET. By following the step-by-step guide and using the provided source code, you can create a new document, insert an area chart, add series data, and save the document with the chart.

Aspose.Words for .NET provides a powerful API for working with charts in Word documents. With just a few lines of code, you can create professional-looking area charts and customize them according to your requirements. Area charts are commonly used to display the magnitude and trends of data over time or categories.

By using Aspose.Words for .NET, you can automate the process of generating documents with area charts, saving time and effort in manual document creation. The library offers a wide range of chart types and customization options, allowing you to create visually appealing and informative charts in your Word documents.

### FAQs

#### Q1. What is Aspose.Words for .NET?
Aspose.Words for .NET is a powerful document processing library that enables developers to create, modify, and convert Word documents programmatically in .NET applications. It provides a comprehensive set of APIs for working with document elements, including charts, paragraphs, tables, and more.

#### Q2. How do I install Aspose.Words for .NET?
To install Aspose.Words for .NET, you can use the NuGet package manager in Visual Studio to install the library directly into your project. Simply search for "Aspose.Words" in the NuGet package manager and install the package.

#### Q3. Can I customize the appearance of the area chart?
Yes, using Aspose.Words for .NET, you can customize various aspects of the area chart's appearance. You can modify properties such as chart title, series color, axis labels, and chart area formatting. The library provides a rich set of APIs to control the visual elements of the chart and create a customized look that suits your needs.

#### Q4. Can I add multiple series to the area chart?
Yes, you can add multiple series to the area chart using Aspose.Words for .NET. Each series represents a set of data points that are plotted on the chart. You can add series with different data sets and customize each series individually, including its name, data points, and appearance.

#### Q5. Can I save the document with the inserted area chart in different formats?
Yes, Aspose.Words for .NET allows you to save the document with the inserted area chart in various formats, such as DOCX, PDF, HTML, and more. You can choose the desired output format based on your requirements and use the `Save` method of the `Document` object to save the document. The inserted area chart will be preserved in the saved document.

#### Q6. Can I modify the data and appearance of the area chart after inserting it?
Yes, after inserting the area chart into the document, you can modify its data and appearance using the APIs provided by Aspose.Words for .NET. You can update the series data, change the chart type, customize axis properties, and apply formatting options to create dynamic and interactive charts in your Word documents.