---
title: Create & Customize Chart Using Shape
linktitle: Create & Customize Chart Using Shape
second_title: Aspose.Words Document Processing API
description: Learn how to create and customize a chart using a shape in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-charts/create-chart-using-shape/
---

This tutorial explains how to create a chart using a shape in a Word document using Aspose.Words for .NET.

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

## Step 3: Insert and Configure a Chart Shape
Insert a chart shape into the document using the `InsertChart` method of the `DocumentBuilder` object. Set the desired chart type and dimensions.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Step 4: Customize the Chart
Customize the chart by modifying various properties such as the chart title and legend.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Step 5: Save the Document
Save the document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Example source code for Create Chart Using Shape using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Please note if null or empty value is specified as title text, auto generated title will be shown.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

That's it! You have successfully created a chart using a shape in a Word document using Aspose.Words for .NET.

## Conclusion
In this tutorial, you have learned how to create a chart using a shape in a Word document using Aspose.Words for .NET. By following the step-by-step guide, you can insert and configure a chart shape, customize its appearance, and save the document. Aspose.Words for .NET provides a comprehensive set of features for working with Word documents and charts, enabling you to create professional-looking and visually appealing charts directly in your .NET applications.

### FAQs

#### Q1. Can I create charts in a Word document using Aspose.Words for .NET?
Yes, with Aspose.Words for .NET, you can create charts in a Word document programmatically. Aspose.Words provides APIs and functionalities to insert various types of charts, customize their appearance, and manipulate chart data.

#### Q2. What chart types are supported by Aspose.Words for .NET?
Aspose.Words for .NET supports a wide range of chart types, including line charts, bar charts, pie charts, area charts, scatter charts, and more. You can choose the appropriate chart type based on your data and visualization requirements.

#### Q3. Can I customize the appearance of the created chart?
Yes, you can customize the appearance of the created chart using Aspose.Words for .NET. You can modify properties such as chart title, legend position, data labels, axis labels, colors, and other visual elements to meet your specific design and formatting needs.

