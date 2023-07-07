---
title: 勾选多行标签对齐
linktitle: 勾选多行标签对齐
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在图表轴中对齐刻度多行标签。
type: docs
weight: 10
url: /zh/net/programming-with-charts/tick-multi-line-label-alignment/
---

本教程介绍如何使用 Aspose.Words for .NET 设置图表轴中刻度多行标签的对齐方式。提供的源代码演示了如何创建图表、访问轴以及修改刻度标签对齐方式。

## 第 1 步：设置项目

确保您具备以下先决条件：

- 已安装 Aspose.Words for .NET 库。您可以从 Aspose 官方网站下载它或使用 NuGet 包管理器来安装它。
- 将保存输出文档的文档目录路径。

## 步骤 2：创建一个新文档并插入图表

创建一个新的`Document`对象和一个`DocumentBuilder`构建文档。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

接下来，使用`InsertChart`的方法`DocumentBuilder`将散点图插入文档中。

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## 步骤 3：设置刻度标签对齐方式

要设置刻度多行标签的对齐方式，请访问`AxisX`图表的属性并设置`TickLabelAlignment`属性到所需的对齐方式。在本例中，我们将对齐方式设置为`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## 步骤 4：保存文档

最后，使用命令将文档保存到指定目录`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

这样就完成了使用Aspose.Words for .NET设置刻度线多行标签对齐方式的实现。

### 使用 Aspose.Words for .NET 进行勾选多行标签对齐的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	//该属性仅对多行标签有效。
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```