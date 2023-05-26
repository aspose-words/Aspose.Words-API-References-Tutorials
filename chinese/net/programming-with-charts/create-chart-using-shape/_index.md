---
title: 使用形状创建图表
linktitle: 使用形状创建图表
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 使用 Word 文档中的形状创建和自定义图表。
type: docs
weight: 10
url: /zh/net/programming-with-charts/create-chart-using-shape/
---

本教程解释了如何使用 Aspose.Words for .NET 在 Word 文档中使用形状创建图表。

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

## 第 3 步：插入和配置图表形状
使用`InsertChart`的方法`DocumentBuilder`目的。设置所需的图表类型和维度。

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 第 4 步：自定义图表
通过修改图表标题和图例等各种属性来自定义图表。

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## 第 5 步：保存文档
使用 将文档保存到指定目录`Save`方法。提供具有适当文件扩展名的所需文件名。在此示例中，我们将文档保存为“WorkingWithCharts.CreateChartUsingShape.docx”。

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### 使用 Aspose.Words for .NET 使用形状创建图表的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	//请注意，如果将 null 或空值指定为标题文本，将显示自动生成的标题。
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 在 Word 文档中使用形状成功创建了图表。