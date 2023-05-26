---
title: 图表数据标签
linktitle: 图表数据标签
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在图表中添加和自定义数据标签，以提供有关数据点的额外信息。
type: docs
weight: 10
url: /zh/net/programming-with-charts/chart-data-label/
---

本教程解释了如何使用 Aspose.Words for .NET 在图表中添加和自定义数据标签。数据标签提供有关图表中数据点的附加信息。

## 先决条件
要学习本教程，您需要具备以下条件：

- 安装了 Aspose.Words for .NET 库。
- C# 的基本知识和使用 Word 文档。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建新文档和 DocumentBuilder
创建一个新的实例`Document`类和一个`DocumentBuilder`对象来处理文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：插入和配置图表
使用`InsertChart`的方法`DocumentBuilder`目的。设置所需的图表类型和维度。

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
使用 将文档保存到指定目录`Save`方法。提供具有适当文件扩展名的所需文件名。在此示例中，我们将文档保存为“WorkingWithCharts.ChartDataLabel.docx”。

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
	//默认情况下，当您将数据标签添加到饼图中的数据点时，为数据标签显示引出线
	//位于远离数据点末端的位置。引导线在数据标签和它的标签之间创建视觉连接
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