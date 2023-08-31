---
title: Customize Single Chart Series In A Chart
linktitle: Customize Single Chart Series In A Chart
second_title: Aspose.Words Document Processing API
description: Learn how to customize single chart series in a chart using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-charts/single-chart-series/
---

This tutorial explains how to use Aspose.Words for .NET to customize single chart series in a chart. The provided source code demonstrates how to create a chart, access specific series, and modify their properties.

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

## Step 3: Access and customize chart series

To modify single chart series, you need to access the `ChartSeries` objects of the chart.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Step 4: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

This completes the implementation of customizing a single chart series using Aspose.Words for .NET.

### Example source code for Single Chart Series using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// You can also specify whether the line connecting the points on the chart shall be smoothed using Catmull-Rom splines.
	series0.Smooth = true;
	series1.Smooth = true;
	// Specifies whether by default the parent element shall inverts its colors if the value is negative.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## Conclusion

In this tutorial, you have learned how to customize a single chart series in a chart using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can create a new document, insert a line chart, access specific chart series, and modify their properties to achieve the desired customization.

Aspose.Words for .NET provides powerful features to manipulate charts in Word documents. By accessing individual chart series, you can apply specific modifications to customize their appearance and behavior. This allows you to change the series name, enable smoothing of the chart line, customize markers for data points, invert colors for negative values, and more, to enhance the visual representation of your chart.

Customizing a single chart series provides you with the flexibility to highlight specific data or emphasize particular trends within your chart. With Aspose.Words for .NET, you can easily access and modify chart series properties, enabling you to create visually appealing and informative charts in your Word documents.

### FAQs

#### Q1. Can I customize multiple chart series in a chart?
Yes, you can customize multiple chart series in a chart using Aspose.Words for .NET. By accessing the `ChartSeries` objects within the chart, you can select and modify multiple series based on their indices or specific criteria. Use a loop or individual assignments to modify the desired properties for each chart series. This way, you can apply different customizations to multiple series within the same chart.

#### Q2. How can I change the name of a chart series?
To change the name of a chart series in a chart using Aspose.Words for .NET, you need to access the `Name` property of the `ChartSeries` object and set it to the desired name. The series name is typically displayed in the chart legend or data labels, providing a descriptive label for the series. By modifying the series name, you can provide meaningful names that reflect the data represented by each series.

#### Q3. What is chart series smoothing?
Chart series smoothing is a visual enhancement technique that allows you to create a smooth line connecting the points on the chart. It applies a smoothing algorithm, such as Catmull-Rom splines, to interpolate between data points and create a visually pleasing curve. To enable series smoothing in a chart using Aspose.Words for .NET, access the `Smooth` property of the `ChartSeries` object and set it to `true`. Smoothing can be useful for displaying trends or patterns in data with irregular fluctuations.

#### Q4. How can I customize markers for data points in a chart series?
To customize markers for data points in a chart series using Aspose.Words for .NET, you need to access the `Marker` property of the `ChartSeries` object and modify its properties such as `Symbol` and `Size`. Markers are visual indicators placed on the chart to represent individual data points. You can choose from a variety of built-in marker symbols and adjust their size to highlight or differentiate specific data points within the series.

#### Q5. Can I invert colors for negative values in a chart series?
Yes, you can invert colors for negative values in a chart series using Aspose.Words for .NET. By setting the `InvertIfNegative` property of the `ChartSeries` object to `true`, the colors for data points with negative values will be inverted, making them visually distinct from positive values. This feature can be useful when comparing positive and negative values in a chart series, providing clear differentiation between the two.