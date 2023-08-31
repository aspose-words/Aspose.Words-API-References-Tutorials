---
title: Number Format For Axis In A Chart
linktitle: Number Format For Axis In A Chart
second_title: Aspose.Words Document Processing API
description: Learn how to set the number format for an axis in a chart using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-charts/number-format-for-axis/
---

This tutorial explains how to use Aspose.Words for .NET to set the number format for an axis in a chart. The provided source code demonstrates how to create a chart, add series data, and format the axis labels.

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

Next, use the `InsertChart` method of the `DocumentBuilder` to insert a column chart into the document.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Step 3: Add series data to the chart

Add series data to the chart. In this example, we'll add five items with their corresponding values.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Step 4: Format the axis labels

To set the number format for the Y-axis labels, access the `AxisY` property of the chart and set the `NumberFormat.FormatCode` property to the desired format. In this example, we set the format to "#,##0" to display numbers with thousands separators.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Step 5: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

This completes the implementation of setting the number format for the axis using Aspose.Words for .NET.

### Example source code for Number Format For Axis using Aspose.Words for .NET 

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
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Conclusion

In this tutorial, you have learned how to set the number format for an axis in a chart using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can create a new document, insert a column chart, add series data, and format the axis labels to display numbers in a specific format.

Aspose.Words for .NET provides powerful features to customize the appearance of charts in Word documents. By setting the number format for the axis labels, you can control how numbers are displayed, including options such as decimal places, thousands separators, currency symbols, and more. This allows you to present numeric data in a clear and meaningful way.

With Aspose.Words for .NET, you have the flexibility to format various aspects of the chart, including the axis labels. By setting the number format for the axis, you can ensure consistency and improve the readability of the chart, making it easier for users to interpret the values represented.

### FAQs

#### Q1. What is the number format for an axis in a chart?
The number format for an axis in a chart refers to the formatting applied to the numeric values displayed on the axis. It allows you to control how numbers are presented, including options such as decimal places, thousands separators, currency symbols, percentage signs, and more. By setting the number format, you can customize the appearance of numeric data in the chart to suit your specific requirements.

#### Q2. How can I set the number format for the axis labels?
To set the number format for the axis labels in a chart using Aspose.Words for .NET, you can access the `AxisY` property of the chart and set the `NumberFormat.FormatCode` property to the desired format code. The format code follows the syntax of standard numeric formatting patterns and determines how the numbers are displayed. For example, you can use "#,##0.00" to display numbers with two decimal places and thousands separators.

#### Q3. Can I set different number formats for the X-axis and Y-axis labels?
Yes, you can set different number formats for the X-axis and Y-axis labels using Aspose.Words for .NET. Access the respective axis (`AxisX` for X-axis or `AxisY` for Y-axis) of the chart and modify the `NumberFormat.FormatCode` property individually for each axis. This allows you to apply different number formats to the labels on each axis based on your specific requirements.

#### Q4. What are some common number format codes I can use?
Aspose.Words for .NET supports a wide range of number format codes that you can use to format the axis labels in a chart. Some common format codes include:

- `0` or `#` - Displays the number with no decimal places.
- `0.00` or `#.00` - Displays the number with two decimal places.
- `#,##0` - Displays the number with thousands separators.
- `"€"0.00` - Displays the number with the Euro currency symbol and two decimal places.
- `"%"0` - Displays the number as a percentage.

You can find more information about number [format codes](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) in API Reference of Aspose.Words for .NET.

#### Q5. Can I customize other properties of the axis labels?
Yes, Aspose.Words for .NET provides a wide range of properties to customize the appearance and behavior of axis labels. In addition to the number format, you can modify properties such as font, size, color, orientation, alignment, and more. This allows you to fully customize the axis labels to match your desired style and presentation requirements.