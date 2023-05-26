---
title: 插入气泡图
linktitle: 插入气泡图
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将气泡图插入文档。添加具有 X、Y 和气泡大小值的系列数据。
type: docs
weight: 10
url: /zh/net/programming-with-charts/insert-bubble-chart/
---

本教程解释了如何使用 Aspose.Words for .NET 将气泡图插入到文档中。提供的源代码演示了如何创建图表、添加系列数据和保存文档。

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

接下来，使用`InsertChart`的方法`DocumentBuilder`在文档中插入气泡图。

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## 第 3 步：将系列数据添加到图表

将系列数据添加到图表中。在此示例中，我们将添加三个具有相应 X、Y 和气泡大小值的数据点。

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## 第 4 步：保存文档

最后，使用 将文件保存到指定目录`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

这样就完成了使用Aspose.Words for .NET 插入气泡图的实现。

### 使用 Aspose.Words for .NET 插入气泡图的示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```