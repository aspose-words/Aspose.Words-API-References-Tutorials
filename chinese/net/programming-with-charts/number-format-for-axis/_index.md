---
title: 轴的数字格式
linktitle: 轴的数字格式
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 为图表中的轴设置数字格式。
type: docs
weight: 10
url: /zh/net/programming-with-charts/number-format-for-axis/
---

本教程解释了如何使用 Aspose.Words for .NET 设置图表中轴的数字格式。提供的源代码演示了如何创建图表、添加系列数据和格式化轴标签。

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

接下来，使用`InsertChart`的方法`DocumentBuilder`将柱形图插入到文档中。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 第 3 步：将系列数据添加到图表

将系列数据添加到图表中。在此示例中，我们将添加五个项目及其相应的值。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## 第 4 步：格式化轴标签

要设置 Y 轴标签的数字格式，请访问`AxisY`图表的属性并设置`NumberFormat.FormatCode`属性为所需的格式。在此示例中，我们将格式设置为“#,##0”以显示带有千位分隔符的数字。

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## 第 5 步：保存文档

最后，使用 将文件保存到指定目录`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

这样就完成了使用Aspose.Words for .NET设置坐标轴的数字格式的实现。

### 使用 Aspose.Words for .NET 的轴数字格式示例源代码 

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
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```