---
title: 图表数据标签
linktitle: 图表数据标签
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在图表中添加和自定义数据标签，以提供有关数据点的附加信息。
type: docs
weight: 10
url: /zh/net/programming-with-charts/chart-data-label/
---

本教程介绍如何使用 Aspose.Words for .NET 在图表中添加和自定义数据标签。数据标签提供有关图表中数据点的附加信息。

## 先决条件
要学习本教程，您需要具备以下条件：

- 已安装 Aspose.Words for .NET 库。
- C# 和使用 Word 文档的基本知识。

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

## 第 3 步：插入并配置图表
使用以下命令将图表插入到文档中`InsertChart`的方法`DocumentBuilder`目的。设置所需的图表类型和尺寸。

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## 第 4 步：自定义数据标签
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

## 第 5 步：保存文档
使用以下命令将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档另存为“WorkingWithCharts.ChartDataLabel.docx”。

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### 使用 Aspose.Words for .NET 的图表数据标签的示例源代码 

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
	//默认情况下，当您向饼图中的数据点添加数据标签时，会显示以下数据标签的引导线：
	//位于远离数据点末尾的位置。引导线在数据标签及其内容之间创建视觉连接
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

就是这样！您已使用 Aspose.Words for .NET 在图表中成功添加和自定义数据标签。