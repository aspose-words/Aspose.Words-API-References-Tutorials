---
title: 将日期时间值添加到图表的轴
linktitle: 将日期时间值添加到图表的轴
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将日期时间值添加到图表的轴。
type: docs
weight: 10
url: /zh/net/programming-with-charts/date-time-values-to-axis/
---

本教程介绍如何使用 Aspose.Words for .NET 将日期时间值添加到图表的轴。

## 先决条件
要学习本教程，您需要具备以下条件：

- 已安装 Aspose.Words for .NET 库。
- C# 和 Word 文档文字处理的基础知识。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`与要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建新文档和 DocumentBuilder
创建一个新实例`Document`类和一个`DocumentBuilder`对象使用该文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：插入并配置图表形状
使用以下命令将图表形状插入到文档中`InsertChart`的方法`DocumentBuilder`目的。设置所需的图表类型和尺寸。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## 第 4 步：将数据添加到图表中
将数据添加到图表系列，包括日期时间值。

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## 第 5 步：配置轴
配置图表的 X 轴以显示日期时间值。

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## 第 6 步：保存文档
使用以下命令将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档另存为“WorkingWithCharts.DateTimeValuesToAxis.docx”。

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### 使用 Aspose.Words for .NET 将日期时间值转至轴的示例源代码 

```csharp
	//文档目录的路径
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
	//将主要单位设置为一周，将次要单位设置为一天。
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

此示例代码创建一个新的Word文档，插入X轴上带有日期时间值的柱形图，并将文档保存到指定目录。

## 结论
在本教程中，您学习了如何使用 Aspose.Words for .NET 将日期时间值添加到图表的轴。通过遵循分步指南，您可以创建图表、向系列添加日期时间值以及配置轴以准确显示日期时间值。 Aspose.Words for .NET 为 Word 文档中的图表进行文字处理提供了一组强大的功能，使您可以有效地表示和可视化具有日期时间值的数据。

### 常见问题解答

#### Q1.我可以使用 Aspose.Words for .NET 将日期时间值添加到图表的轴吗？
是的，使用 Aspose.Words for .NET，您可以在 Word 文档中的图表轴上添加和显示日期时间值。 Aspose.Words 提供 API 和功能来处理各种图表类型并自定义其外观，包括处理轴上的日期时间值。

#### Q2。如何向图表系列添加日期时间值？
要将日期时间值添加到图表系列中，您可以使用`Add`图表系列的方法。提供日期时间值数组作为类别（X 轴）数据，以及相应的系列值。这允许您在图表上绘制具有日期时间值的数据点。

#### Q3。如何配置轴以显示日期时间值？
您可以通过设置适当的属性来配置图表的轴以显示日期时间值。例如，您可以使用以下命令指定轴的最小值和最大值`Scaling.Minimum`和`Scaling.Maximum`属性，分别。此外，您可以设置主要和次要单位来定义轴的间隔和刻度线。
