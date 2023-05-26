---
title: 轴的边界
linktitle: 轴的边界
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 设置图表中轴的边界，从而控制轴上显示的值的范围。
type: docs
weight: 10
url: /zh/net/programming-with-charts/bounds-of-axis/
---

本教程解释了如何使用 Aspose.Words for .NET 设置图表中轴的边界。通过插入图表、添加系列数据和配置轴缩放，您可以定义轴的最小值和最大值。

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
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 第 4 步：添加系列数据
清除图表中的任何现有系列并添加新的系列数据。在这个例子中，我们添加了一个带有标签“Item 1”到“Item 5”和相应值的系列。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 第 5 步：设置轴的边界
通过使用设置最小值和最大值来配置 Y 轴的缩放比例`Scaling.Minimum`和`Scaling.Maximum`轴的属性。

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## 第 6 步：保存文档
使用 将文档保存到指定目录`Save`方法。提供具有适当文件扩展名的所需文件名。在此示例中，我们将文档保存为“WorkingWithCharts.BoundsOfAxis.docx”。

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### 使用 Aspose.Words for .NET 的 Bounds Of Axis 示例源代码 

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
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功设置了图表中轴的边界。