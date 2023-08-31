---
title: Customize A Single Chart Data Point In A Chart
linktitle: Customize A Single Chart Data Point In A Chart
second_title: Aspose.Words Document Processing API
description: Learn how to customize a single data point in a chart using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-charts/single-chart-data-point/
---

This tutorial explains how to use Aspose.Words for .NET to customize a single data point in a chart. The provided source code demonstrates how to create a chart, access specific data points, and modify their properties.

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

Next, use the `InsertChart` method of the `DocumentBuilder` to insert a line chart into the document.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Step 3: Access and customize data points

To modify individual data points, you need to access the `ChartDataPointCollection` of the series and select the desired data point using the index.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## Step 4: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

This completes the implementation of customizing a single data point in a chart using Aspose.Words for .NET.

### Example source code for Single Chart Data Point using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## Conclusion

In this tutorial, you have learned how to customize a single data point in a chart using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can create a new document, insert a line chart, access specific data points within the chart series, and modify their properties to achieve the desired customization.

Aspose.Words for .NET provides powerful features to manipulate charts in Word documents. By accessing individual data points within a chart series, you can apply specific modifications to customize their appearance and behavior. This allows you to highlight specific data points, change marker symbols, adjust marker sizes, and more, to enhance the visual representation of your chart.

Customizing individual data points gives you the flexibility to emphasize important data or highlight specific trends in your chart. With Aspose.Words for .NET, you can easily access and modify data points in various chart types, enabling you to create visually appealing and informative charts in your Word documents.

### FAQs

#### Q1. Can I customize multiple data points in a chart?
Yes, you can customize multiple data points in a chart using Aspose.Words for .NET. By accessing the `ChartDataPointCollection` of a series, you can select and modify multiple data points based on their indices. Use a loop or individual assignments to modify the desired properties for each data point. This way, you can apply different customizations to multiple data points within the same chart.

#### Q2. How can I change the marker symbol for a data point?
To change the marker symbol for a data point in a chart using Aspose.Words for .NET, you need to access the `Marker` property of the `ChartDataPoint` object and set the `Symbol` property to the desired marker symbol. Marker symbols represent the shape or icon used to represent each data point on the chart. You can choose from a variety of built-in marker symbols such as circle, square, diamond, triangle, star, and more.

#### Q3. Can I adjust the size of a data point marker?
Yes, you can adjust the size of a data point marker in a chart using Aspose.Words for .NET. Access the `Marker` property of the `ChartDataPoint` object and set the `Size` property to the desired marker size. The size of the marker is typically specified in points, where a larger value represents a larger marker size. Adjusting the marker size allows you to emphasize specific data points or differentiate them based on their significance.

#### Q4. What other properties can I modify for a data point?
Aspose.Words for .NET provides a range of properties that you can modify for a data point in a chart. Some of the commonly modified properties include the marker symbol, marker size, marker color, data label visibility, explosion, invert if negative, and more. These properties allow you to customize the appearance, behavior, and interactivity of individual data points, enabling you to create charts tailored to your specific requirements.

#### Q5. Can I customize data points in other chart types?
Yes, you can customize data points in various chart types using Aspose.Words for .NET. While this tutorial demonstrates customizing data points in a line chart, you can apply similar techniques to other chart types such as column charts, bar charts, pie charts, and more. The process involves accessing the series and data points within the chart and modifying their properties accordingly.