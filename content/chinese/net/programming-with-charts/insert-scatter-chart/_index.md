---
title: 在 Word 文档中插入散点图
linktitle: 在 Word 文档中插入散点图
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将散点图插入文档。添加带有 X 和 Y 坐标的系列数据。
type: docs
weight: 10
url: /zh/net/programming-with-charts/insert-scatter-chart/
---

本教程讲解如何使用 Aspose.Words for .NET 将散点图插入文档。提供的源代码演示了如何创建图表、添加系列数据以及保存文档。

## 步骤 1：设置项目

确保您满足以下先决条件：

- 已安装 Aspose.Words for .NET 库。您可以使用 NuGet 包管理器下载并安装它。
- 保存输出文档的文档目录路径。

## 步骤 2：创建新文档并插入图表

创建一个新的`Document`对象和一个`DocumentBuilder`来创建文档。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

接下来，使用`InsertChart`方法`DocumentBuilder`在文档中插入散点图。

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## 步骤 3：向图表添加系列数据

向图表添加系列数据。在此示例中，我们将添加两组 X 和 Y 坐标。

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## 步骤 4：保存文档

最后，使用`Save`方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

这样就完成了使用Aspose.Words for .NET插入散点图的实现。

### 使用 Aspose.Words for .NET 插入散点图的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## 结论

在本教程中，您学习了如何使用 Aspose.Words for .NET 将散点图插入 Word 文档。通过遵循分步指南并使用提供的源代码，您可以创建新文档、插入散点图、添加具有 X 和 Y 坐标的系列数据，并使用图表保存文档。

Aspose.Words for .NET 提供了全面的 API，用于在 Word 文档中使用图表进行文字处理。散点图对于使用两个数值变量可视化和分析数据非常有用。使用 Aspose.Words for .NET，您可以轻松创建散点图来表示 X 和 Y 值之间的关系并识别数据中的模式或趋势。

通过使用 Aspose.Words for .NET，您可以自动生成带有散点图的文档，从而节省手动创建文档的时间和精力。该库提供多种图表类型，包括散点图，并提供各种自定义选项以根据您的需要定制图表的外观。

### 常见问题解答

#### Q1. 什么是散点图？
散点图是一种显示两个数值变量之间关系的图表。它由绘制在坐标网格上的一系列点组成，其中一个变量表示在 X 轴上，另一个变量表示在 Y 轴上。散点图用于识别两组数据点之间的模式、相关性或趋势。

#### Q2. 我可以向散点图添加多个系列吗？
是的，您可以使用 Aspose.Words for .NET 将多个系列添加到散点图。每个系列代表一组具有各自 X 和 Y 坐标的数据点。通过添加多个系列，您可以比较和分析同一张散点图中的不同数据集，从而提供数据的全面视图。

#### Q3. 我可以自定义散点图的外观吗？
是的，使用 Aspose.Words for .NET，您可以自定义散点图外观的各个方面。您可以修改系列颜色、标记形状、轴标签和图表区域格式等属性。该库提供了一组丰富的 API 来控制图表的视觉元素并创建适合您需求的自定义外观。

#### Q4. 我可以将插入散点图的文档保存为不同的格式吗？
是的，Aspose.Words for .NET 允许您以各种格式保存插入散点图的文档，例如 DOCX、PDF、HTML 等。您可以根据需要选择所需的输出格式，并使用`Save`方法`Document`对象来保存文档。插入的散点图将保留在保存的文档中。

#### Q5. 插入散点图后可以修改其数据和外观吗？
是的，将散点图插入文档后，您可以使用 Aspose.Words for .NET 提供的 API 修改其数据和外观。您可以使用新的 X 和 Y 坐标更新系列数据，更改标记形状和颜色，自定义轴属性，并应用格式选项以在 Word 文档中创建动态和交互式图表。