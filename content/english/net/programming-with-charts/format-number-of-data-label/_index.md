---
title: Format Number Of Data Label In A Chart
linktitle: Format Number Of Data Label In A Chart
second_title: Aspose.Words Document Processing API
description: Learn how to format the number of data labels in a chart using Aspose.Words for .NET. Customize number formats for data labels easily.
type: docs
weight: 10
url: /net/programming-with-charts/format-number-of-data-label/
---

This tutorial explains how to use Aspose.Words for .NET to format the number of data labels in a chart. The provided source code demonstrates how to create a chart, add series data, and customize the number format of data labels.

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

Next, insert a chart into the document using the `InsertChart` method of the `DocumentBuilder`. In this example, we'll insert a line chart.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Step 3: Add series data to the chart

Add series data to the chart. In this example, we'll add three categories and their corresponding values.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Step 4: Customize the number format of data labels

To format the number of data labels, access the `DataLabels` collection associated with the series.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

In this example, we set different number formats for each data label. The first data label is formatted as a currency, the second as a date, and the third as a percentage.

## Step 5: Save the document

Finally, save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

This completes the implementation of formatting the number of data labels in a chart using Aspose.Words for .NET.

### Example source code for Format Number Of Data Label using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Delete default generated series.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Or you can set format code to be linked to a source cell,
	// in this case NumberFormat will be reset to general and inherited from a source cell.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Conclusion

In this tutorial, you have learned how to format the number of data labels in a chart using Aspose.Words for .NET. By following the step-by-step guide and using the provided source code, you can create a chart, add series data, and customize the number format of data labels according to your requirements.

Aspose.Words for .NET provides a comprehensive API for Words Processing with charts in Word documents, allowing you to manipulate various aspects of the chart, including data labels. By accessing the `DataLabels` collection associated with a series, you can customize the number format of individual data labels.

The API allows you to control the display of values, set different number formats for each data label, and link the number format to a source cell. This flexibility enables you to present numeric data in charts with the desired formatting, such as currency symbols, date formats, and percentage values.

By using Aspose.Words for .NET, you can incorporate powerful charting capabilities into your .NET applications and generate professional-looking documents with fully formatted charts and data labels.

### FAQs

#### Q1. What is Aspose.Words for .NET?
Aspose.Words for .NET is a feature-rich document processing library that enables developers to create, manipulate, and save Word documents programmatically in .NET applications. It provides a wide range of features for Words Processing with document elements, including charts and data labels.

#### Q2. How can I install Aspose.Words for .NET?
You can install Aspose.Words for .NET by downloading it by using the NuGet package manager in Visual Studio. Simply search for "Aspose.Words" in the NuGet package manager and install it into your project.

#### Q3. Can I format other aspects of the chart using Aspose.Words for .NET?
Yes, Aspose.Words for .NET provides extensive capabilities for formatting various aspects of a chart. In addition to data labels, you can customize chart type, series data, axis properties, legend, title, plot area, and many other elements of the chart. The API offers fine-grained control over chart appearance and formatting.

#### Q4. Can I apply different number formats to different data labels in the same series?
Yes, Aspose.Words for .NET allows you to apply different number formats to individual data labels within the same series. By accessing the `DataLabels` collection associated with a series, you can set the `FormatCode` property of each data label to specify the desired number format. This allows you to present numeric values in different formats within the same chart.

#### Q5. Can I use custom number formats for data labels?
Yes, Aspose.Words for .NET supports custom number formats for data labels. You can specify the desired number format by setting the `FormatCode` property of a data label to a custom format code. This gives you the flexibility to apply a wide range of number formats, such as currency symbols, date formats, percentage values, and more.

#### Q6. Can I save the chart with formatted data labels in different formats?
Yes, Aspose.Words for .NET allows you to save the document containing the chart with formatted data labels in various formats, such as DOCX, PDF, HTML, and more. You can choose the appropriate format based on your requirements and use the `Save` method of the `Document` object to save the document. The formatted data labels will be preserved in the saved document.