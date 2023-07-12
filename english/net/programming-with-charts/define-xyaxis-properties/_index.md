---
title: Define XY Axis Properties In A Chart
linktitle: Define XY Axis Properties In A Chart
second_title: Aspose.Words Document Processing API
description: Learn how to define XY axis properties in a chart using Aspose.Words for .NET. Customization options for the X and Y axes are demonstrated.
type: docs
weight: 10
url: /net/programming-with-charts/define-xyaxis-properties/
---

This tutorial explains how to use Aspose.Words for .NET to define properties for the X and Y axes in a chart. The provided source code demonstrates how to create a chart, add series data, and customize the axis properties.

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

Next, insert a chart into the document using the `InsertChart` method of the `DocumentBuilder`. In this example, we'll insert an area chart.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Step 3: Add series data to the chart

Add series data to the chart. In this example, we'll add five data points with corresponding dates and values.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## Step 4: Customize X and Y axis properties

To customize the properties of the X and Y axes, access the `ChartAxis` objects associated with the chart.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

Modify the properties of the `xAxis` and `yAxis` objects to set the desired options for the X and Y axes. In this example, we'll demonstrate some common properties that can be customized.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Step 5: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

This completes the implementation of defining XY axis properties in a chart using Aspose.Words for .NET.

### Example source code for Define XYAxis Properties using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Insert chart
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// Change the X axis to be category instead of date, so all the points will be put with equal interval on the X axis.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; // Measured in display units of the Y axis (hundreds).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Conclusion

In this tutorial, you have learned how to define properties for the X and Y axes in a chart using Aspose.Words for .NET. By following the step-by-step guide, you can create a chart, add series data, and customize the axis properties to meet your specific requirements. Aspose.Words for .NET provides a comprehensive API for working with charts in Word documents, allowing you to manipulate various aspects of the chart, including the axes.

By accessing the `ChartAxis` objects associated with the chart, you can modify properties such as the category type, axis crosses, tick marks, label positions, scaling, and more. This flexibility enables you to tailor the appearance and behavior of the chart's axes to effectively present your data.

By using Aspose.Words for .NET, you can seamlessly integrate chart creation and customization capabilities into your .NET applications and automate the generation of professional-looking documents with rich visualizations.

### FAQs

#### Q1. What is Aspose.Words for .NET?
Aspose.Words for .NET is a powerful document processing library that enables developers to create, manipulate, and save Word documents programmatically in .NET applications. It provides a wide range of features for working with document elements, including charts.

#### Q2. How can I install Aspose.Words for .NET?
You can install Aspose.Words for .NET by downloading it by using the NuGet package manager in Visual Studio. Simply search for "Aspose.Words" in the NuGet package manager and install it into your project.

#### Q3. Can I customize other aspects of the chart using Aspose.Words for .NET?
Yes, Aspose.Words for .NET provides extensive capabilities for customizing various aspects of a chart. In addition to defining axis properties, you can modify chart type, data series, legend, title, plot area, data labels, and many other elements of the chart. The API offers fine-grained control over chart appearance and behavior.

#### Q4. Can I create different types of charts using Aspose.Words for .NET?
Yes, Aspose.Words for .NET supports a wide range of chart types, including area, bar, line, pie, scatter, and more. You can use the `ChartType` enumeration to specify the desired chart type when inserting a chart shape into a Word document.

#### Q5. Can I save the chart in different formats?
Yes, Aspose.Words for .NET allows you to save the document containing the chart in various formats, such as DOCX, PDF, HTML, and more. You can choose the appropriate format based on your requirements and use the `Save` method of the `Document` object to save the document.

#### Q6. Can I apply these techniques to multiple charts in a document?
Yes, you can apply these techniques to multiple charts in a document by repeating the necessary steps for each chart. You can create separate `Chart` and `ChartAxis` objects for each chart and customize their properties accordingly. Aspose.Words for .NET provides full support for working with multiple charts in a single document.