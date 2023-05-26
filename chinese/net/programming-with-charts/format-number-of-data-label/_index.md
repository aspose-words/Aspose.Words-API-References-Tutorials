---
title: 数据标签格式编号
linktitle: 数据标签格式编号
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 格式化图表中数据标签的数量。轻松自定义数据标签的数字格式。
type: docs
weight: 10
url: /zh/net/programming-with-charts/format-number-of-data-label/
---

本教程解释了如何使用 Aspose.Words for .NET 来格式化图表中数据标签的数量。提供的源代码演示了如何创建图表、添加系列数据以及自定义数据标签的数字格式。

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

接下来，使用`InsertChart`的方法`DocumentBuilder`.在这个例子中，我们将插入一个折线图。

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## 第 3 步：将系列数据添加到图表

将系列数据添加到图表中。在此示例中，我们将添加三个类别及其对应的值。

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## 第四步：自定义数据标签的数字格式

要格式化数据标签的数量，请访问`DataLabels`与该系列相关的集合。

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

在这个例子中，我们为每个数据标签设置了不同的数字格式。第一个数据标签的格式为货币，第二个为日期，第三个为百分比。

## 第 5 步：保存文档

最后，使用 将文件保存到指定目录`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

这样就完成了使用 Aspose.Words for .NET 格式化图表中数据标签数量的实现。

### 使用 Aspose.Words for .NET 的格式数据标签数量示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	//删除默认生成的系列。
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	//或者您可以将格式代码设置为链接到源单元格，
	//在这种情况下，NumberFormat 将重置为一般格式并从源单元格继承。
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```