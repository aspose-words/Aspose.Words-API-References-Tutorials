---
title: 使用形状创建和自定义图表
linktitle: 使用形状创建和自定义图表
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建并自定义形状图表。
type: docs
weight: 10
url: /zh/net/programming-with-charts/create-chart-using-shape/
---

本教程讲解如何使用 Aspose.Words for .NET 使用 Word 文档中的形状创建图表。

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

## 步骤 3：插入并配置图表形状
使用`InsertChart`方法`DocumentBuilder`对象。设置所需的图表类型和尺寸。

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 步骤 4：自定义图表
通过修改图表标题和图例等各种属性来定制图表。

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## 步骤 5：保存文档
使用将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档保存为“WorkingWithCharts.CreateChartUsingShape.docx”。

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
	//请注意，如果将标题文本指定为空值或空值，则将显示自动生成的标题。
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

就是这样！您已成功使用 Aspose.Words for .NET 在 Word 文档中使用形状创建了图表。

## 结论
在本教程中，您学习了如何使用 Aspose.Words for .NET 在 Word 文档中使用形状创建图表。按照分步指南，您可以插入和配置图表形状、自定义其外观并保存文档。Aspose.Words for .NET 为 Word 文档和图表的文字处理提供了一套全面的功能，使您能够直接在 .NET 应用程序中创建具有专业外观和视觉吸引力的图表。

### 常见问题解答

#### Q1. 我可以使用 Aspose.Words for .NET 在 Word 文档中创建图表吗？
是的，使用 Aspose.Words for .NET，您可以通过编程方式在 Word 文档中创建图表。Aspose.Words 提供 API 和功能来插入各种类型的图表、自定义其外观以及操作图表数据。

#### Q2. Aspose.Words for .NET 支持哪些图表类型？
Aspose.Words for .NET 支持多种图表类型，包括折线图、条形图、饼图、面积图、散点图等。您可以根据数据和可视化要求选择适当的图表类型。

#### Q3. 我可以自定义创建的图表的外观吗？
是的，您可以使用 Aspose.Words for .NET 自定义所创建图表的外观。您可以修改图表标题、图例位置、数据标签、轴标签、颜色和其他视觉元素等属性，以满足您的特定设计和格式需求。
