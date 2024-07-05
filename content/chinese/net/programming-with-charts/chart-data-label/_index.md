---
title: 自定义图表数据标签
linktitle: 自定义图表数据标签
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在图表中添加和自定义数据标签以提供有关数据点的附加信息。
type: docs
weight: 10
url: /zh/net/programming-with-charts/chart-data-label/
---

本教程介绍如何使用 Aspose.Words for .NET 在图表中添加和自定义数据标签。数据标签提供有关图表中数据点的其他信息。

## 先决条件
要遵循本教程，您需要满足以下条件：

- 已安装 Aspose.Words for .NET 库。
- 具备 C# 和 Word 文档文字处理的基本知识。

## 步骤 1：设置文档目录
首先设置文档目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`替换为您想要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：创建新文档和 DocumentBuilder
创建一个新的实例`Document`类和一个`DocumentBuilder`对象来处理该文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：插入并配置图表
使用`InsertChart`方法`DocumentBuilder`对象。设置所需的图表类型和尺寸。

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## 步骤 4：自定义数据标签
访问图表系列的数据标签集合并修改各种属性以自定义数据标签的外观。

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## 步骤 5：保存文档
使用将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档保存为“WorkingWithCharts.ChartDataLabel.docx”。

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### 使用 Aspose.Words for .NET 的图表数据标签示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	//默认情况下，当您向饼图中的数据点添加数据标签时，会显示数据标签的引线，这些引线
	//引线位于数据点末端的远处。引线在数据标签和其
	//对应的数据点。
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

就是这样！您已成功使用 Aspose.Words for .NET 在图表中添加和自定义数据标签。

## 结论
在本教程中，您学习了如何使用 Aspose.Words for .NET 在图表中添加和自定义数据标签。按照分步指南，您可以插入图表、访问数据标签集合并修改属性以自定义数据标签的外观。Aspose.Words for .NET 为 Word 文档和图表的文字处理提供了强大的 API，使您能够使用自定义数据标签创建具有视觉吸引力和信息丰富的图表。

### 常见问题解答

#### Q1. 图表中的数据标签是什么？
图表中的数据标签提供有关图表中显示的数据点的其他信息。它们可以显示值、类别、系列名称、百分比或其他相关详细信息，具体取决于图表类型和配置。

#### Q2. 我可以自定义数据标签的外观吗？
是的，您可以自定义图表中数据标签的外观。Aspose.Words for .NET 提供了修改数据标签各种属性的选项，例如显示图例键、引线、类别名称、系列名称、值等。您还可以设置分隔符并格式化标签以满足您的特定要求。

#### Q3. 我可以向任何图表类型添加数据标签吗？
是的，您可以将数据标签添加到各种类型的图表中，包括条形图、饼图、折线图等。添加和自定义数据标签的过程可能略有不同，具体取决于图表类型以及您使用的库或工具。
