---
title: 在Word文档中插入散点图
linktitle: 在Word文档中插入散点图
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将散点图插入文档中。添加带有 X 和 Y 坐标的系列数据。
type: docs
weight: 10
url: /zh/net/programming-with-charts/insert-scatter-chart/
---

本教程介绍如何使用 Aspose.Words for .NET 将散点图插入文档中。提供的源代码演示了如何创建图表、添加系列数据以及保存文档。

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

接下来，使用`InsertChart`的方法`DocumentBuilder`将散点图插入文档中。

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## 步骤 3：将系列数据添加到图表中

将系列数据添加到图表中。在此示例中，我们将添加两组 X 和 Y 坐标。

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## 步骤 4：保存文档

最后，使用命令将文档保存到指定目录`Save`的方法`Document`目的。

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

在本教程中，您学习了如何使用 Aspose.Words for .NET 将散点图插入到 Word 文档中。通过遵循分步指南并使用提供的源代码，您可以创建一个新文档、插入散点图、添加具有 X 和 Y 坐标的系列数据，以及使用图表保存文档。

Aspose.Words for .NET 为 Word 文档中的图表进行文字处理提供了全面的 API。散点图对于可视化和分析具有两个数值变量的数据非常有用。使用 Aspose.Words for .NET，您可以轻松创建表示 X 和 Y 值之间关系的散点图，并识别数据中的模式或趋势。

通过使用 Aspose.Words for .NET，您可以自动生成带有散点图的文档的过程，从而节省手动文档创建的时间和精力。该库提供了多种图表类型，包括散点图，并提供了各种自定义选项以根据您的需求定制图表的外观。

### 常见问题解答

#### Q1.什么是散点图？
散点图是一种显示两个数值变量之间关系的图表。它由绘制在坐标网格上的一系列点组成，一个变量表示在 X 轴上，另一个变量表示在 Y 轴上。散点图用于识别两组数据点之间的模式、相关性或趋势。

#### Q2。我可以向散点图添加多个系列吗？
是的，您可以使用 Aspose.Words for .NET 将多个系列添加到散点图中。每个系列代表一组数据点及其各自的 X 和 Y 坐标。通过添加多个系列，您可以在同一散点图中比较和分析不同的数据集，从而提供数据的全面视图。

#### Q3。我可以自定义散点图的外观吗？
是的，使用 Aspose.Words for .NET，您可以自定义散点图外观的各个方面。您可以修改系列颜色、标记形状、轴标签和图表区域格式等属性。该库提供了一组丰富的 API 来控制图表的视觉元素并创建适合您需求的自定义外观。

#### Q4。我可以将插入散点图的文档保存为不同格式吗？
是的，Aspose.Words for .NET 允许您以各种格式保存带有插入的散点图的文档，例如 DOCX、PDF、HTML 等。您可以根据您的要求选择所需的输出格式并使用`Save`的方法`Document`对象来保存文档。插入的散点图将保留在保存的文档中。

#### Q5.插入散点图后可以修改数据和外观吗？
是的，将散点图插入文档后，您可以使用 Aspose.Words for .NET 提供的 API 修改其数据和外观。您可以使用新的 X 和 Y 坐标更新系列数据、更改标记形状和颜色、自定义轴属性以及应用格式设置选项以在 Word 文档中创建动态和交互式图表。