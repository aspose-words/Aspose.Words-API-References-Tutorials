---
title: 图表中轴的界限
linktitle: 图表中轴的界限
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 设置图表中轴的边界，控制轴上显示的值的范围。
type: docs
weight: 10
url: /zh/net/programming-with-charts/bounds-of-axis/
---

本教程介绍如何使用 Aspose.Words for .NET 设置图表中轴的边界。通过插入图表、添加系列数据和配置轴缩放，您可以定义轴的最小值和最大值。

## 先决条件
要学习本教程，您需要具备以下条件：

- 已安装 Aspose.Words for .NET 库。
- C# 和 Word 文档文字处理的基础知识。

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
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 第 4 步：添加系列数据
清除图表中的所有现有系列并添加新的系列数据。在此示例中，我们添加一个带有标签“Item 1”到“Item 5”以及相应值的系列。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 第5步：设置轴的边界
通过使用设置最小值和最大值来配置 Y 轴的缩放比例`Scaling.Minimum`和`Scaling.Maximum`轴的属性。

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## 第 6 步：保存文档
使用以下命令将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档另存为“WorkingWithCharts.BoundsOfAxis.docx”。

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

就是这样！您已使用 Aspose.Words for .NET 成功设置图表中轴的边界。

## 结论
在本教程中，您学习了如何使用 Aspose.Words for .NET 设置图表中轴的边界。通过遵循分步指南，您可以插入和配置图表、添加系列数据以及定义轴缩放的最小值和最大值。 Aspose.Words for .NET 提供了强大而灵活的 API，用于 Word 文档的文字处理，使您可以轻松创建动态且具有视觉吸引力的图表。


### 常见问题解答

#### Q1.什么是 Aspose.Words for .NET？
Aspose.Words for .NET 是一个库，允许开发人员以编程方式处理 Word 文档。它提供了广泛的用于创建、操作和保存 Word 文档的特性和功能。

#### Q2。如何安装 Aspose.Words for .NET？
要安装 Aspose.Words for .NET，您可以使用 Visual Studio 中的 NuGet 包管理器。只需在 NuGet 包管理器中搜索“Aspose.Words”并将其安装到您的项目中即可。

#### Q3。我可以将 Aspose.Words for .NET 与其他编程语言一起使用吗？
不，Aspose.Words for .NET 是专门为 .NET 应用程序设计的。它适用于 C# 和 VB.NET 等编程语言。

#### Q4。使用 Aspose.Words for .NET 是否还有其他先决条件？
除了安装 Aspose.Words for .NET 库之外，您还应该具备 C# 编程和 Word 文档文字处理的基本知识。熟悉 .NET 框架也会有所帮助。
