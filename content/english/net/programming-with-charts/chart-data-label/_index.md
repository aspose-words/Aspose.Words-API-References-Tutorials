---
title: Customize Chart Data Label
linktitle: Customize Chart Data Label
second_title: Aspose.Words Document Processing API
description: Learn how to add and customize data labels in a chart using Aspose.Words for .NET to provide additional information about data points.
type: docs
weight: 10
url: /net/programming-with-charts/chart-data-label/
---

This tutorial explains how to add and customize data labels in a chart using Aspose.Words for .NET. Data labels provide additional information about the data points in a chart.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and Words Processing with Word documents.

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
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## Step 4: Customize Data Labels
Access the data labels collection of the chart series and modify various properties to customize the appearance of the data labels.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## Step 5: Save the Document
Save the document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithCharts.ChartDataLabel.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Example source code for Chart Data Label using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// By default, when you add data labels to the data points in a pie chart, leader lines are displayed for data labels that are
	// positioned far outside the end of data points. Leader lines create a visual connection between a data label and its 
	// corresponding data point.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

That's it! You have successfully added and customized data labels in a chart using Aspose.Words for .NET.

## Conclusion
In this tutorial, you have learned how to add and customize data labels in a chart using Aspose.Words for .NET. By following the step-by-step guide, you can insert a chart, access the data labels collection, and modify the properties to customize the appearance of the data labels. Aspose.Words for .NET provides a powerful API for Words Processing with Word documents and charts, enabling you to create visually appealing and informative charts with customized data labels.

### FAQs

#### Q1. What are data labels in a chart?
Data labels in a chart provide additional information about the data points represented in the chart. They can display values, categories, series names, percentages, or other relevant details depending on the chart type and configuration.

#### Q2. Can I customize the appearance of data labels?
Yes, you can customize the appearance of data labels in a chart. Aspose.Words for .NET provides options to modify various properties of data labels, such as showing legend keys, leader lines, category names, series names, values, and more. You can also set separators and format the labels to meet your specific requirements.

#### Q3. Can I add data labels to any chart type?
Yes, you can add data labels to various types of charts, including bar charts, pie charts, line charts, and more. The process of adding and customizing data labels may vary slightly depending on the chart type and the library or tool you are using.

