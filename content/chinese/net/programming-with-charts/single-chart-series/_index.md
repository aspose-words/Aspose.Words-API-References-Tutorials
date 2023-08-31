---
title: 自定义图表中的单个图表系列
linktitle: 自定义图表中的单个图表系列
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 自定义图表中的单个图表系列。
type: docs
weight: 10
url: /zh/net/programming-with-charts/single-chart-series/
---

本教程介绍如何使用 Aspose.Words for .NET 自定义图表中的单个图表系列。提供的源代码演示了如何创建图表、访问特定系列以及修改其属性。

## 第 1 步：设置项目

确保您具备以下先决条件：

- 已安装 Aspose.Words for .NET 库。您可以使用 NuGet 包管理器下载并安装它。
- 将保存输出文档的文档目录路径。

## 步骤 2：创建一个新文档并插入图表

创建一个新的`Document`对象和一个`DocumentBuilder`构建文档。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

接下来，使用`InsertChart`的方法`DocumentBuilder`将折线图插入文档中。

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 第 3 步：访问并自定义图表系列

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

## 步骤 4：保存文档

最后，使用命令将文档保存到指定目录`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

这样就完成了使用 Aspose.Words for .NET 自定义单个图表系列的实现。

### 使用 Aspose.Words for .NET 的单图表系列的示例源代码 

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
	//您还可以指定是否应使用 Catmull-Rom 样条线来平滑连接图表上的点的线。
	series0.Smooth = true;
	series1.Smooth = true;
	//指定如果值为负数，父元素是否默认反转其颜色。
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## 结论

在本教程中，您学习了如何使用 Aspose.Words for .NET 在图表中自定义单个图表系列。通过遵循分步指南并利用提供的源代码，您可以创建新文档、插入折线图、访问特定图表系列并修改其属性以实现所需的自定义。

Aspose.Words for .NET 提供了强大的功能来操作 Word 文档中的图表。通过访问各个图表系列，您可以应用特定的修改来自定义其外观和行为。这允许您更改系列名称、启用图表线平滑、自定义数据点标记、反转负值的颜色等等，以增强图表的视觉表示。

自定义单个图表系列使您可以灵活地突出显示图表中的特定数据或强调特定趋势。使用 Aspose.Words for .NET，您可以轻松访问和修改图表系列属性，从而使您能够在 Word 文档中创建具有视觉吸引力且信息丰富的图表。

### 常见问题解答

#### Q1.我可以在一个图表中自定义多个图表系列吗？
是的，您可以使用 Aspose.Words for .NET 在图表中自定义多个图表系列。通过访问`ChartSeries`图表中的对象，您可以根据其指数或特定条件选择和修改多个系列。使用循环或单独分配来修改每个图表系列所需的属性。这样，您可以将不同的自定义应用于同一图表中的多个系列。

#### Q2。如何更改图表系列的名称？
要使用 Aspose.Words for .NET 更改图表中图表系列的名称，您需要访问`Name`的财产`ChartSeries`对象并将其设置为所需的名称。系列名称通常显示在图表图例或数据标签中，为该系列提供描述性标签。通过修改系列名称，您可以提供有意义的名称来反映每个系列所代表的数据。

#### Q3。什么是图表系列平滑？
图表系列平滑是一种视觉增强技术，可让您创建连接图表上的点的平滑线。它应用平滑算法（例如 Catmull-Rom 样条线）在数据点之间进行插值并创建视觉上令人愉悦的曲线。要使用 Aspose.Words for .NET 在图表中启用系列平滑，请访问`Smooth`的财产`ChartSeries`对象并将其设置为`true`。平滑可用于显示具有不规则波动的数据的趋势或模式。

#### Q4。如何为图表系列中的数据点自定义标记？
要使用 Aspose.Words for .NET 自定义图表系列中数据点的标记，您需要访问`Marker`的财产`ChartSeries`对象并修改其属性，例如`Symbol`和`Size`。标记是放置在图表上的视觉指示器，用于表示各个数据点。您可以从各种内置标记符号中进行选择，并调整其大小以突出显示或区分系列中的特定数据点。

#### Q5.我可以反转图表系列中负值的颜色吗？
是的，您可以使用 Aspose.Words for .NET 反转图表系列中负值的颜色。通过设置`InvertIfNegative`的财产`ChartSeries`反对`true`，具有负值的数据点的颜色将被反转，使它们在视觉上与正值不同。在比较图表系列中的正值和负值时，此功能非常有用，可以清楚地区分两者。