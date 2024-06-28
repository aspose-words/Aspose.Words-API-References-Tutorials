---
title: 圖表中軸的界限
linktitle: 圖表中軸的界限
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 設定圖表中軸的邊界，控制軸上顯示的值的範圍。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/bounds-of-axis/
---

本教學介紹如何使用 Aspose.Words for .NET 設定圖表中軸的邊界。透過插入圖表、新增系列資料以及配置軸縮放比例，您可以定義軸的最小值和最大值。

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

## 第 3 步：插入並配置圖表
使用以下命令將圖表插入到文件中`InsertChart`的方法`DocumentBuilder`目的。設定所需的圖表類型和尺寸。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 第 4 步：新增系列數據
清除圖表中的所有現有系列並新增新的系列資料。在此範例中，我們新增一個標籤「Item 1」到「Item 5」以及對應值的系列。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 第5步：設定軸的邊界
透過使用設定最小值和最大值來配置 Y 軸的縮放比例`Scaling.Minimum`和`Scaling.Maximum`軸的屬性。

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## 第 6 步：儲存文檔
使用以下命令將文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithCharts.BoundsOfAxis.docx」。

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### 使用 Aspose.Words for .NET 的 Bounds Of Axis 範例原始碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 成功設定圖表中軸的邊界。

## 結論
在本教學中，您學習如何使用 Aspose.Words for .NET 設定圖表中軸的邊界。透過遵循逐步指南，您可以插入和配置圖表、新增系列資料以及定義軸縮放的最小值和最大值。 Aspose.Words for .NET 提供了強大且靈活的 API，用於 Word 文件的文字處理，讓您可以輕鬆建立動態且具有視覺吸引力的圖表。


### 常見問題解答

#### Q1.什麼是 Aspose.Words for .NET？
Aspose.Words for .NET 是一個函式庫，允許開發人員以程式設計方式處理 Word 文件。它提供了廣泛的用於建立、操作和保存 Word 文件的特性和功能。

#### Q2。如何安裝 Aspose.Words for .NET？
若要安裝 Aspose.Words for .NET，您可以使用 Visual Studio 中的 NuGet 套件管理器。只需在 NuGet 套件管理器中搜尋“Apose.Words”並將其安裝到您的專案中即可。

#### Q3。我可以將 Aspose.Words for .NET 與其他程式語言一起使用嗎？
不，Aspose.Words for .NET 是專門為 .NET 應用程式設計的。它適用於 C# 和 VB.NET 等程式語言。

#### Q4。使用 Aspose.Words for .NET 是否有其他先決條件？
除了安裝 Aspose.Words for .NET 程式庫之外，您還應該具備 C# 程式設計和 Word 文件文字處理的基本知識。熟悉 .NET 框架也會有所幫助。
