---
title: Add Date Time Values To Axis Of A Chart
linktitle: Add Date Time Values To Axis Of A Chart
second_title: Aspose.Words Document Processing API
description: Learn how to add date time values to the axis of a chart using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-charts/date-time-values-to-axis/
---

This tutorial explains how to add date time values to the axis of a chart using Aspose.Words for .NET.

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
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Step 4: Add Data to the Chart
Add data to the chart series, including date time values.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Step 5: Configure the Axis
Configure the X-axis of the chart to display the date time values.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Step 6: Save the Document
Save the document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithCharts.DateTimeValuesToAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Example source code for Date Time Values To Axis using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Set major units to a week and minor units to a day.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

This example code creates a new Word document, inserts a column chart with date time values on the X-axis, and saves the document to the specified directory.

## Conclusion
In this tutorial, you have learned how to add date time values to the axis of a chart using Aspose.Words for .NET. By following the step-by-step guide, you can create a chart, add date time values to the series, and configure the axis to display the date time values accurately. Aspose.Words for .NET provides a powerful set of features for working with charts in Word documents, allowing you to represent and visualize data with date time values effectively.

### FAQs

#### Q1. Can I add date time values to the axis of a chart using Aspose.Words for .NET?
Yes, with Aspose.Words for .NET, you can add and display date time values on the axis of a chart in a Word document. Aspose.Words provides APIs and functionalities to work with various chart types and customize their appearance, including handling date time values on the axis.

#### Q2. How do I add date time values to the chart series?
To add date time values to the chart series, you can use the `Add` method of the chart's series. Provide an array of date time values as the category (X-axis) data, along with the corresponding series values. This allows you to plot data points with date time values on the chart.

#### Q3. How can I configure the axis to display date time values?
You can configure the axis of the chart to display date time values by setting the appropriate properties. For example, you can specify the minimum and maximum values for the axis using the `Scaling.Minimum` and `Scaling.Maximum` properties, respectively. Additionally, you can set the major and minor units to define the interval and tick marks for the axis.

