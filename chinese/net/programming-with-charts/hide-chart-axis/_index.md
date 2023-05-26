---
title: 隐藏图表轴
linktitle: 隐藏图表轴
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 隐藏文档中的图表轴。隐藏轴以获得更清晰、更集中的图表显示。
type: docs
weight: 10
url: /zh/net/programming-with-charts/hide-chart-axis/
---

本教程解释了如何使用 Aspose.Words for .NET 隐藏文档中的图表轴。提供的源代码演示了如何创建图表、添加系列数据和隐藏图表轴。

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

接下来，使用`InsertChart`的方法`DocumentBuilder`.在此示例中，我们将插入一个柱形图。

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

## 第 4 步：隐藏图表轴

要隐藏图表轴，请访问`AxisY`图表的属性并设置`Hidden`财产给`true`.

```csharp
chart.AxisY.Hidden = true;
```

在这个例子中，我们隐藏了图表的 Y 轴。

## 第 5 步：保存文档

最后，使用 将文件保存到指定目录`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

这样就完成了使用Aspose.Words for .NET隐藏图表轴的实现。

### 使用 Aspose.Words for .NET 隐藏图表轴的示例源代码 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```