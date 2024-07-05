---
title: 图表中轴的数字格式
linktitle: 图表中轴的数字格式
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 设置图表中轴的数字格式。
type: docs
weight: 10
url: /zh/net/programming-with-charts/number-format-for-axis/
---

本教程讲解如何使用 Aspose.Words for .NET 设置图表中轴的数字格式。提供的源代码演示了如何创建图表、添加系列数据和设置轴标签的格式。

## 步骤 1：设置项目

确保您满足以下先决条件：

- 已安装 Aspose.Words for .NET 库。您可以使用 NuGet 包管理器下载并安装它。
- 保存输出文档的文档目录路径。

## 步骤 2：创建新文档并插入图表

创建一个新的`Document`对象和一个`DocumentBuilder`来创建文档。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

接下来，使用`InsertChart`方法`DocumentBuilder`在文档中插入柱形图。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 步骤 3：向图表添加系列数据

向图表添加系列数据。在此示例中，我们将添加五个项目及其相应的值。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## 步骤 4：设置轴标签的格式

要设置 Y 轴标签的数字格式，请访问`AxisY`图表的属性并设置`NumberFormat.FormatCode`属性设置为所需格式。在此示例中，我们将格式设置为“#,##0”，以显示带有千位分隔符的数字。

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## 步骤 5：保存文档

最后，使用`Save`方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

这样就完成了使用 Aspose.Words for .NET 设置轴的数字格式的实现。

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

## 结论

在本教程中，您学习了如何使用 Aspose.Words for .NET 设置图表中轴的数字格式。通过遵循分步指南并利用提供的源代码，您可以创建新文档、插入柱形图、添加系列数据并格式化轴标签以显示特定格式的数字。

Aspose.Words for .NET 提供强大的功能来自定义 Word 文档中图表的外观。通过设置轴标签的数字格式，您可以控制数字的显示方式，包括小数位、千位分隔符、货币符号等选项。这允许您以清晰而有意义的方式呈现数字数据。

使用 Aspose.Words for .NET，您可以灵活地格式化图表的各个方面，包括轴标签。通过设置轴的数字格式，您可以确保一致性并提高图表的可读性，使用户更容易解释所表示的值。

### 常见问题解答

#### Q1. 图表中轴的数字格式是什么？
图表中轴的数字格式是指应用于轴上显示的数值的格式。它允许您控制数字的呈现方式，包括小数位、千位分隔符、货币符号、百分号等选项。通过设置数字格式，您可以自定义图表中数字数据的外观以满足您的特定要求。

#### Q2. 如何设置轴标签的数字格式？
要使用 Aspose.Words for .NET 设置图表中轴标签的数字格式，您可以访问`AxisY`图表的属性并设置`NumberFormat.FormatCode`属性设置为所需的格式代码。格式代码遵循标准数字格式模式的语法，并确定数字的显示方式。例如，您可以使用“#,##0.00”显示带有两位小数和千位分隔符的数字。

#### Q3. 我可以为 X 轴和 Y 轴标签设置不同的数字格式吗？
是的，您可以使用 Aspose.Words for .NET 为 X 轴和 Y 轴标签设置不同的数字格式。访问相应的轴 (`AxisX`对于 X 轴或`AxisY`图表的`NumberFormat.FormatCode`为每个轴单独设置属性。这样，您就可以根据具体要求为每个轴上的标签应用不同的数字格式。

#### Q4. 我可以使用哪些常见的数字格式代码？
Aspose.Words for .NET 支持多种数字格式代码，您可以使用这些代码来格式化图表中的轴标签。一些常见的格式代码包括：

- `0`或者`#` - 显示没有小数的数字。
- `0.00`或者`#.00` - 显示带有两位小数的数字。
- `#,##0` 显示带有千位分隔符的数字。
- `"€"0.00` - 显示带有欧元货币符号和两位小数的数字。
- `"%"0` - 以百分比显示数字。

您可以找到有关号码的更多信息[格式代码](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/)在 Aspose.Words for .NET 的 API 参考中。

#### Q5. 我可以自定义轴标签的其他属性吗？
是的，Aspose.Words for .NET 提供了多种属性来自定义轴标签的外观和行为。除了数字格式之外，您还可以修改字体、大小、颜色、方向、对齐等属性。这允许您完全自定义轴标签以匹配您想要的样式和演示要求。