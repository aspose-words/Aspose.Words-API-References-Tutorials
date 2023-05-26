---
title: 定义 XY 轴属性
linktitle: 定义 XY 轴属性
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在图表中定义 XY 轴属性。演示了 X 轴和 Y 轴的自定义选项。
type: docs
weight: 10
url: /zh/net/programming-with-charts/define-xyaxis-properties/
---

本教程解释了如何使用 Aspose.Words for .NET 来定义图表中 X 轴和 Y 轴的属性。提供的源代码演示了如何创建图表、添加系列数据和自定义轴属性。

## 第 1 步：设置项目

确保您具有以下先决条件：

- 安装了 Aspose.Words for .NET 库。您可以从 Aspose 官方网站下载或使用 NuGet 包管理器安装它。
- 将保存输出文档的文档目录路径。

## 第 2 步：创建新文档并插入图表

创建一个新的`Document`对象和一个`DocumentBuilder`构建文档。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

接下来，使用`InsertChart`的方法`DocumentBuilder`.在这个例子中，我们将插入一个面积图。

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## 第 3 步：将系列数据添加到图表

将系列数据添加到图表中。在此示例中，我们将添加五个具有相应日期和值的数据点。

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

## 第 4 步：自定义 X 和 Y 轴属性

要自定义 X 轴和 Y 轴的属性，请访问`ChartAxis`与图表关联的对象。

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

修改属性`xAxis`和`yAxis`对象来为 X 和 Y 轴设置所需的选项。在此示例中，我们将演示一些可以自定义的通用属性。

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

最后，使用 将文件保存到指定目录`Save`的方法`Document`目的。

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
	//将 X 轴更改为类别而不是日期，因此所有点将以相等的间隔放在 X 轴上。
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