---
title: Hide Chart Axis In A Word Document
linktitle: Hide Chart Axis In A Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to hide the chart axis in a document using Aspose.Words for .NET. Hide the axis for a cleaner and more focused chart display.
type: docs
weight: 10
url: /net/programming-with-charts/hide-chart-axis/
---

This tutorial explains how to use Aspose.Words for .NET to hide the chart axis in a document. The provided source code demonstrates how to create a chart, add series data, and hide the chart axis.

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

Next, insert a chart into the document using the `InsertChart` method of the `DocumentBuilder`. In this example, we'll insert a column chart.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Step 3: Add series data to the chart

Add series data to the chart. In this example, we'll add five items and their corresponding values.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Step 4: Hide the chart axis

To hide the chart axis, access the `AxisY` property of the chart and set the `Hidden` property to `true`.

```csharp
chart.AxisY.Hidden = true;
```

In this example, we hide the Y-axis of the chart.

## Step 5: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

This completes the implementation of hiding the chart axis using Aspose.Words for .NET.

### Example source code for Hide Chart Axis using Aspose.Words for .NET 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## Conclusion

In this tutorial, you have learned how to hide the chart axis in a Word document using Aspose.Words for .NET. By following the step-by-step guide and using the provided source code, you can create a chart, add series data, and hide the chart axis to achieve the desired visual effect.

Aspose.Words for .NET provides a comprehensive API for working with charts in Word documents, allowing you to manipulate various aspects of the chart, including axis properties. By accessing the `AxisY` property of the chart, you can hide the Y-axis to remove it from the chart visualization.

Hiding the chart axis can be useful when you want to focus on the chart data without the distraction of the axis lines and labels. It provides a cleaner and more minimalist appearance to the chart.

By using Aspose.Words for .NET, you can easily incorporate charting capabilities into your .NET applications and generate professional-looking documents with customized charts and hidden chart axes.

### FAQs

#### Q1. What is Aspose.Words for .NET?
Aspose.Words for .NET is a powerful document processing library that enables developers to create, manipulate, and save Word documents programmatically in .NET applications. It provides a wide range of features for working with document elements, including charts and chart axes.

#### Q2. How can I install Aspose.Words for .NET?
You can install Aspose.Words for .NET by downloading it by using the NuGet package manager in Visual Studio. Simply search for "Aspose.Words" in the NuGet package manager and install it into your project.

#### Q3. Can I hide both the X-axis and Y-axis of a chart?
Yes, you can hide both the X-axis and Y-axis of a chart using Aspose.Words for .NET. To hide the X-axis, you can access the `AxisX` property of the chart and set the `Hidden` property to `true`. Similarly, to hide the Y-axis, you can access the `AxisY` property and set the `Hidden` property to `true`. This allows you to remove both axes from the chart visualization.

#### Q4. Can I show the axis again after hiding it?
Yes, you can show the chart axis again after hiding it using Aspose.Words for .NET. To show a hidden axis, simply set the `Hidden` property of the corresponding `AxisX` or `AxisY` object to `false`. This will make the axis visible again in the chart.

#### Q5. Can I customize other properties of the chart axis?
Yes, Aspose.Words for .NET allows you to customize various properties of the chart axis, such as the axis title, labels, line color, and more. By accessing the `AxisX` and `AxisY` properties of the chart, you can modify properties like `Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, and many others. This gives you fine-grained control over the appearance and behavior of the chart axis.

#### Q6. Can I save the chart with the hidden axis in different file formats?
Yes, Aspose.Words for .NET allows you to save the document containing the chart with a hidden axis in various file formats, such as DOCX, PDF, HTML, and more. You can choose the desired output format based on your requirements and use the `Save` method of the `Document` object to save the document. The hidden axis will be preserved in the saved document.