---
title: Set Default Options For Data Labels In A Chart
linktitle: Set Default Options For Data Labels In A Chart
second_title: Aspose.Words Document Processing API
description: Learn how to set default options for data labels in a chart using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-charts/default-options-for-data-labels/
---

This tutorial explains how to use Aspose.Words for .NET to set default options for data labels in a chart. The code provided demonstrates how to create a chart, add data series, and customize the data labels using Aspose.Words.

## Step 1: Set up the project

Before we begin, make sure you have the following requirements in place:

- Aspose.Words for .NET library installed. You can download it using NuGet package manager to install it.
- A document directory path where the output document will be saved.

## Step 2: Create a new document and insert a chart

First, let's create a new `Document` object and a `DocumentBuilder` to build the document.

```csharp
// Path to your document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Next, we insert a chart into the document using the `InsertChart` method of the `DocumentBuilder`. In this example, we'll insert a pie chart.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Step 3: Add data series to the chart

Now, let's add a data series to the chart. In this example, we'll add three categories and their corresponding values.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Step 4: Customize data labels

To customize the data labels in the chart, we need to access the `ChartDataLabelCollection` object associated with the series.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

We can then modify various properties of the `labels` object to set the desired options for data labels. In this example, we'll enable showing the percentage and value, disable leader lines, and set a custom separator.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Step 5: Save the document

Finally, we save the document to the specified directory using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

This completes the implementation of setting default options for data labels in a chart using Aspose.Words for .NET.

### Example source code for Default Options For Data Labels using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

## Conclusion

In this tutorial, you have learned how to set default options for data labels in a chart using Aspose.Words for .NET. By following the step-by-step guide, you can create a chart, add data series, and customize the data labels to meet your specific requirements. Aspose.Words for .NET provides a powerful API for Words Processing with charts in Word documents, allowing you to manipulate various chart elements and achieve the desired appearance and functionality.

By setting the properties of the `ChartDataLabelCollection` object associated with the chart series, you can control the display of data labels, including options such as showing percentages, values, leader lines, and custom separators. This flexibility enables you to present data effectively and enhance the visual representation of your charts.

### FAQs

#### Q1. What is Aspose.Words for .NET?
Aspose.Words for .NET is a library that enables developers to create, manipulate, and save Word documents programmatically using .NET applications. It provides a wide range of features for Words Processing with document elements, including charts.

#### Q2. How can I install Aspose.Words for .NET?
You can install Aspose.Words for .NET by downloading it by using NuGet package manager in Visual Studio. Simply search for "Aspose.Words" in the NuGet package manager and install it into your project.

#### Q3. Can I customize other aspects of the chart using Aspose.Words for .NET?
Yes, Aspose.Words for .NET allows you to customize various aspects of a chart, such as chart type, axis labels, legend, plot area, and more. You can access and modify different properties of the chart object to achieve the desired appearance and behavior.

#### Q4. Can I save the chart in different formats?
Yes, Aspose.Words for .NET supports saving the document containing the chart in various formats, including DOCX, PDF, HTML, and more. You can choose the appropriate format based on your requirements and use the `Save` method of the `Document` object to save the document.

#### Q5. Can I apply these techniques to other chart types?
Yes, the techniques described in this tutorial can be applied to other chart types supported by Aspose.Words for .NET. The key is to access the relevant objects and properties specific to the chart type you are Words Processing with.