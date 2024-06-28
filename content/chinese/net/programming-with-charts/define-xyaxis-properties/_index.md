---
title: 在图表中定义 XY 轴属性
linktitle: 在图表中定义 XY 轴属性
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在图表中定义 XY 轴属性。演示了 X 轴和 Y 轴的定制选项。
type: docs
weight: 10
url: /zh/net/programming-with-charts/define-xyaxis-properties/
---

本教程介绍如何使用 Aspose.Words for .NET 定义图表中 X 轴和 Y 轴的属性。提供的源代码演示了如何创建图表、添加系列数据以及自定义轴属性。

## 第 1 步：设置项目

确保您具备以下先决条件：

- 已安装 Aspose.Words for .NET 库。您可以使用 NuGet 包管理器下载并安装它。
- 将保存输出文档的文档目录路径。

## 步骤2：创建一个新文档并插入图表。

创建一个新的`Document`对象和一个`DocumentBuilder`构建文档。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

接下来，使用以下命令将图表插入到文档中`InsertChart`的方法`DocumentBuilder`。在此示例中，我们将插入面积图。

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## 步骤 3：将系列数据添加到图表中

将系列数据添加到图表中。在此示例中，我们将添加五个数据点以及相应的日期和值。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## 步骤 4：自定义 X 和 Y 轴属性

要自定义 X 轴和 Y 轴的属性，请访问`ChartAxis`与图表关联的对象。

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

修改属性`xAxis`和`yAxis`对象来设置 X 轴和 Y 轴所需的选项。在此示例中，我们将演示一些可以自定义的常见属性。

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## 第 5 步：保存文档

最后，使用命令将文档保存到指定目录`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

这样就完成了使用 Aspose.Words for .NET 在图表中定义 XY 轴属性的实现。

### 使用 Aspose.Words for .NET 定义 XYAxis 属性的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//插入图表
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	//将 X 轴更改为类别而不是日期，这样所有的点将在 X 轴上等间隔放置。
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //以 Y 轴的显示单位（百）测量。
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## 结论

在本教程中，您学习了如何使用 Aspose.Words for .NET 定义图表中 X 轴和 Y 轴的属性。通过遵循分步指南，您可以创建图表、添加系列数据并自定义轴属性以满足您的特定要求。 Aspose.Words for .NET 为 Word 文档中的图表进行文字处理提供了全面的 API，允许您操作图表的各个方面，包括轴。

通过访问`ChartAxis`与图表关联的对象，您可以修改属性，例如类别类型、轴交叉、刻度线、标签位置、缩放比例等。这种灵活性使您能够定制图表轴的外观和行为，以有效地呈现您的数据。

通过使用 Aspose.Words for .NET，您可以将图表创建和自定义功能无缝集成到您的 .NET 应用程序中，并自动生成具有丰富可视化效果的专业文档。

### 常见问题解答

#### Q1.什么是 Aspose.Words for .NET？
Aspose.Words for .NET 是一个功能强大的文档处理库，使开发人员能够在 .NET 应用程序中以编程方式创建、操作和保存 Word 文档。它为文档元素（包括图表）的文字处理提供了广泛的功能。

#### Q2。如何安装 Aspose.Words for .NET？
您可以使用 Visual Studio 中的 NuGet 包管理器下载 Aspose.Words for .NET 来安装它。只需在 NuGet 包管理器中搜索“Apose.Words”并将其安装到您的项目中即可。

#### Q3。我可以使用 Aspose.Words for .NET 自定义图表的其他方面吗？
是的，Aspose.Words for .NET 提供了广泛的功能来自定义图表的各个方面。除了定义轴属性之外，您还可以修改图表类型、数据系列、图例、标题、绘图区域、数据标签和图表的许多其他元素。该 API 提供对图表外观和行为的细粒度控制。

#### Q4。我可以使用 Aspose.Words for .NET 创建不同类型的图表吗？
是的，Aspose.Words for .NET 支持多种图表类型，包括面积图、条形图、折线图、饼图、散点图等。您可以使用`ChartType`枚举以在将图表形状插入 Word 文档时指定所需的图表类型。

#### Q5.我可以以不同的格式保存图表吗？
是的，Aspose.Words for .NET 允许您以各种格式保存包含图表的文档，例如 DOCX、PDF、HTML 等。您可以根据您的要求选择合适的格式并使用`Save`的方法`Document`对象来保存文档。

#### Q6.我可以将这些技术应用于文档中的多个图表吗？
是的，您可以通过对每个图表重复必要的步骤，将这些技术应用于文档中的多个图表。您可以创建单独的`Chart`和`ChartAxis`每个图表的对象并相应地自定义其属性。 Aspose.Words for .NET 提供对单个文档中多个图表的文字处理的全面支持。