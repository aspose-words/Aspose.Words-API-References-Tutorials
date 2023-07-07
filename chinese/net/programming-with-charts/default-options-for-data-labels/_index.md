---
title: 数据标签的默认选项
linktitle: 数据标签的默认选项
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 设置图表中数据标签的默认选项。
type: docs
weight: 10
url: /zh/net/programming-with-charts/default-options-for-data-labels/
---

本教程介绍如何使用 Aspose.Words for .NET 设置图表中数据标签的默认选项。提供的代码演示了如何使用 Aspose.Words 创建图表、添加数据系列以及自定义数据标签。

## 第 1 步：设置项目

在我们开始之前，请确保您满足以下要求：

- 已安装 Aspose.Words for .NET 库。您可以从 Aspose 官方网站下载它或使用 NuGet 包管理器来安装它。
- 将保存输出文档的文档目录路径。

## 步骤 2：创建一个新文档并插入图表

首先，我们创建一个新的`Document`对象和一个`DocumentBuilder`构建文档。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

接下来，我们使用以下命令将图表插入到文档中`InsertChart`的方法`DocumentBuilder`。在此示例中，我们将插入一个饼图。

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## 步骤 3：将数据系列添加到图表中

现在，让我们向图表添加一个数据系列。在此示例中，我们将添加三个类别及其相应的值。

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## 第 4 步：自定义数据标签

要自定义图表中的数据标签，我们需要访问`ChartDataLabelCollection`与该系列关联的对象。

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

然后我们可以修改它的各种属性`labels`对象来设置数据标签所需的选项。在此示例中，我们将启用显示百分比和值、禁用引导线并设置自定义分隔符。

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## 第 5 步：保存文档

最后，我们使用以下命令将文档保存到指定目录`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

这样就完成了使用 Aspose.Words for .NET 设置图表中数据标签默认选项的实现。

### 使用 Aspose.Words for .NET 的数据标签默认选项的示例源代码 

```csharp
	//文档目录的路径
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