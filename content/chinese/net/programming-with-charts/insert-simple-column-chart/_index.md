---
title: 在 Word 文档中插入简单柱形图
linktitle: 在 Word 文档中插入简单柱形图
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将简单柱形图插入文档。
type: docs
weight: 10
url: /zh/net/programming-with-charts/insert-simple-column-chart/
---

本教程讲解如何使用 Aspose.Words for .NET 将简单柱形图插入文档。提供的源代码演示了如何创建图表、添加系列数据以及保存文档。

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

接下来，使用`InsertChart`方法`DocumentBuilder`在文档中插入柱形图。您可以根据需要指定不同的图表类型和大小。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 步骤 3：向图表添加系列数据

将系列数据添加到图表。在此示例中，我们将添加多个系列，每个系列有两个类别。

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## 步骤 4：保存文档

最后，使用`Save`方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

这样就完成了使用Aspose.Words for .NET插入简单柱形图的实现。

### 使用 Aspose.Words for .NET 插入简单柱形图的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//您可以指定不同的图表类型和大小。
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	//删除默认生成的系列。
	seriesColl.Clear();
	//创建类别名称数组，在本教程中我们有两个类别。
	string[] categories = new string[] { "Category 1", "Category 2" };
	//请注意，数据数组不能为空，并且数组必须大小相同。
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## 结论

在本教程中，您学习了如何使用 Aspose.Words for .NET 将简单的柱形图插入 Word 文档。通过遵循分步指南并使用提供的源代码，您可以创建新文档、插入柱形图、添加具有类别和相应值的多个系列，并将文档与图表一起保存。

Aspose.Words for .NET 提供了强大而灵活的 API，用于在 Word 文档中使用图表进行文字处理。简单的柱形图是一种表示和比较不同类别数据的有效方法。使用 Aspose.Words for .NET，您可以轻松创建带有自定义数据的柱形图，添加多个系列以进行视觉比较，并根据您的要求自定义图表的外观。

通过使用 Aspose.Words for .NET，您可以自动生成带有柱形图的文档，从而节省手动创建文档的时间和精力。该库提供多种图表类型，包括简单柱形图，并提供各种自定义选项以根据您的需要定制图表的外观。

### 常见问题解答

#### Q1. 什么是柱状图？
柱形图是一种使用不同高度的垂直条显示数据的图表。每根柱子代表一个类别，柱子的高度与该类别的值相对应。柱形图通常用于比较不同类别的数据或跟踪随时间的变化。

#### Q2. 我可以向柱形图添加多个系列吗？
是的，使用 Aspose.Words for .NET，您可以向柱形图添加多个系列。每个系列代表一组具有各自类别和值的数据点。通过添加多个系列，您可以在同一柱形图中比较和分析不同的数据集，从而提供数据的全面视图。

#### Q3. 我可以自定义柱状图的外观吗？
是的，Aspose.Words for .NET 允许您自定义柱形图外观的各个方面。您可以修改系列颜色、轴标签、数据标签和图表区域格式等属性。该库提供了一组丰富的 API 来控制图表的视觉元素并创建适合您需求的自定义外观。

#### Q4. 我可以将插入柱形图的文档保存为不同的格式吗？
是的，Aspose.Words for .NET 允许您以各种格式保存插入柱形图的文档，例如 DOCX、PDF、HTML 等。您可以根据需要选择所需的输出格式，并使用`Save`方法`Document`对象保存文档。插入的柱形图将保留在保存的文档中。

#### Q5. 插入柱形图后可以修改其数据和外观吗？
是的，将柱形图插入文档后，您可以使用 Aspose.Words for .NET 提供的 API 修改其数据和外观。您可以使用新类别和值更新系列数据，更改列的颜色和格式，自定义轴属性，并应用各种格式选项以在 Word 文档中创建动态且视觉上吸引人的图表。