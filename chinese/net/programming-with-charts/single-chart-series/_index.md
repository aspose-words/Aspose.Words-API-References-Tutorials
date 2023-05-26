---
title: 单图系列
linktitle: 单图系列
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 自定义图表中的单个图表系列。
type: docs
weight: 10
url: /zh/net/programming-with-charts/single-chart-series/
---

本教程解释了如何使用 Aspose.Words for .NET 自定义图表中的单个图表系列。提供的源代码演示了如何创建图表、访问特定系列以及修改它们的属性。

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

接下来，使用`InsertChart`的方法`DocumentBuilder`在文档中插入折线图。

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 第 3 步：访问和自定义图表系列

要修改单个图表系列，您需要访问`ChartSeries`图表的对象。

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

## 第 4 步：保存文档

最后，使用 将文件保存到指定目录`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

这样就完成了使用Aspose.Words for .NET 自定义单个图表系列的实现。

### 使用 Aspose.Words for .NET 的单图表系列示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	//您还可以指定是否使用 Catmull-Rom 样条平滑连接图表上各点的线。
	series0.Smooth = true;
	series1.Smooth = true;
	//指定如果值为负，父元素是否默认反转其颜色。
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```