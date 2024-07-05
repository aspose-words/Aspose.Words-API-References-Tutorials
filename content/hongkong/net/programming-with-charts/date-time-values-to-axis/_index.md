---
title: 將日期時間值加到圖表的軸
linktitle: 將日期時間值加到圖表的軸
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將日期時間值新增至圖表的軸。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/date-time-values-to-axis/
---

本教學介紹如何使用 Aspose.Words for .NET 將日期時間值新增至圖表的軸。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 Word 文件文字處理的基礎知識。

## 第 1 步：設定文檔目錄
首先設定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與要儲存文件的目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：建立新文件和 DocumentBuilder
建立一個新實例`Document`類別和一個`DocumentBuilder`物件使用該文件。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 3：插入並配置圖表形狀
使用以下命令將圖表形狀插入到文件中`InsertChart`的方法`DocumentBuilder`目的。設定所需的圖表類型和尺寸。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## 第 4 步：將資料加入圖表中
將資料新增至圖表系列，包括日期時間值。

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## 第 5 步：配置軸
配置圖表的 X 軸以顯示日期時間值。

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## 第 6 步：儲存文檔
使用以下命令將文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithCharts.DateTimeValuesToAxis.docx」。

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### 使用 Aspose.Words for .NET 將日期時間值轉至軸的範例原始碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	//將主要單位設定為一周，次要單位設定為一天。
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

此範例程式碼建立一個新的 Word 文檔，插入 X 軸上帶有日期時間值的長條圖，並將文檔儲存到指定目錄。

## 結論
在本教學中，您學習如何使用 Aspose.Words for .NET 將日期時間值新增至圖表的軸。透過遵循逐步指南，您可以建立圖表、為系列新增日期時間值以及配置軸以準確顯示日期時間值。 Aspose.Words for .NET 為 Word 文件中的圖表進行文字處理提供了一組強大的功能，使您可以有效地表示和視覺化具有日期時間值的資料。

### 常見問題解答

#### Q1.我可以使用 Aspose.Words for .NET 將日期時間值新增至圖表的軸嗎？
是的，使用 Aspose.Words for .NET，您可以在 Word 文件中的圖表軸上新增和顯示日期時間值。 Aspose.Words 提供 API 和功能來處理各種圖表類型並自訂其外觀，包括處理軸上的日期時間值。

#### Q2。如何為圖表系列新增日期時間值？
若要將日期時間值新增至圖表系列中，您可以使用`Add`圖表系列的方法。提供日期時間值數組作為類別（X 軸）資料以及對應的系列值。這允許您在圖表上繪製具有日期時間值的資料點。

#### Q3。如何配置軸以顯示日期時間值？
您可以透過設定適當的屬性來配置圖表的軸以顯示日期時間值。例如，您可以使用下列命令指定軸的最小值和最大值`Scaling.Minimum`和`Scaling.Maximum`屬性，分別。此外，您可以設定主要和次要單位來定義軸的間隔和刻度線。
