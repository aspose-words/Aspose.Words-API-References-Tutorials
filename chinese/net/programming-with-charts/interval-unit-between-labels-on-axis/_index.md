---
title: 轴上标签之间的间隔单位
linktitle: 轴上标签之间的间隔单位
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 设置图表轴上标签之间的间隔单位。
type: docs
weight: 10
url: /zh/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

本教程解释了如何使用 Aspose.Words for .NET 设置图表轴上标签之间的间隔单位。提供的源代码演示了如何创建图表、添加系列数据和自定义轴标签。

## 第 1 步：设置项目

确保您具有以下先决条件：

- 安装了 Aspose.Words for .NET 库。您可以从 Aspose 官方网站下载或使用 NuGet 包管理器安装它。
- 将保存输出文档的文档目录路径。

## 第 2 步：创建新文档并插入图表

创建一个新的`Document`对象和一个`DocumentBuilder`构建文档。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

接下来，使用`InsertChart`的方法`DocumentBuilder`将柱形图插入到文档中。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 第 3 步：将系列数据添加到图表

将系列数据添加到图表中。在此示例中，我们将添加五个项目及其相应的值。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 第 4 步：自定义轴标签

要设置 X 轴上标签之间的间隔单位，请访问`AxisX`图表的属性并设置`TickLabelSpacing`属性到所需的值。在本例中，我们将间距设置为 2。

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## 第 5 步：保存文档

最后，使用 将文件保存到指定目录`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

这样就完成了使用Aspose.Words for .NET设置轴上标签之间间隔单位的实现。

### Interval Unit Between Labels On Axis using Aspose.Words for .NET 示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```