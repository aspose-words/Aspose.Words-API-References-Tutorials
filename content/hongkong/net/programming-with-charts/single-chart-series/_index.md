---
title: 自訂圖表中的單一圖表系列
linktitle: 自訂圖表中的單一圖表系列
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 自訂圖表中的單一圖表系列。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/single-chart-series/
---

本教學介紹如何使用 Aspose.Words for .NET 自訂圖表中的單一圖表系列。提供的原始程式碼示範如何建立圖表、存取特定係列以及修改其屬性。

## 第 1 步：設定項目

確保您具備以下先決條件：

- 已安裝 Aspose.Words for .NET 程式庫。您可以使用 NuGet 套件管理員下載並安裝它。
- 將儲存輸出文檔的文檔目錄路徑。

## 步驟 2：建立一個新文件並插入圖表

創建一個新的`Document`物件和一個`DocumentBuilder`建置文檔。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

接下來，使用`InsertChart`的方法`DocumentBuilder`將折線圖插入文件中。

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 第 3 步：訪問並自訂圖表系列

要修改單一圖表系列，您需要訪問`ChartSeries`圖表的物件。

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## 步驟 4：儲存文檔

最後，使用命令將文檔儲存到指定目錄`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

這樣就完成了使用 Aspose.Words for .NET 自訂單一圖表系列的實作。

### 使用 Aspose.Words for .NET 的單圖表系列的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	//您也可以指定是否應使用 Catmull-Rom 樣條線來平滑連接圖表上的點的線。
	series0.Smooth = true;
	series1.Smooth = true;
	//指定如果值為負數，父元素是否預設反轉其顏色。
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## 結論

在本教學中，您學習如何使用 Aspose.Words for .NET 在圖表中自訂單一圖表系列。透過遵循逐步指南並利用提供的原始程式碼，您可以建立新文件、插入折線圖、存取特定圖表系列並修改其屬性以實現所需的自訂。

Aspose.Words for .NET 提供了強大的功能來操作 Word 文件中的圖表。透過存取各個圖表系列，您可以套用特定的修改來自訂其外觀和行為。這允許您更改系列名稱、啟用圖表線平滑、自訂資料點標記、反轉負值的顏色等等，以增強圖表的視覺表示。

自訂單一圖表系列可讓您靈活地突出顯示圖表中的特定數據或強調特定趨勢。使用 Aspose.Words for .NET，您可以輕鬆存取和修改圖表系列屬性，從而使您能夠在 Word 文件中建立具有視覺吸引力且資訊豐富的圖表。

### 常見問題解答

#### Q1.我可以在一個圖表中自訂多個圖表系列嗎？
是的，您可以使用 Aspose.Words for .NET 在圖表中自訂多個圖表系列。透過訪問`ChartSeries`圖表中的對象，您可以根據其指數或特定條件選擇和修改多個系列。使用循環或單獨分配來修改每個圖表系列所需的屬性。這樣，您可以將不同的自訂套用到同一圖表中的多個系列。

#### Q2。如何更改圖表系列的名稱？
要使用 Aspose.Words for .NET 更改圖表中圖表系列的名稱，您需要訪問`Name`的財產`ChartSeries`物件並將其設定為所需的名稱。系列名稱通常顯示在圖表圖例或資料標籤中，為該系列提供描述性標籤。透過修改系列名稱，您可以提供有意義的名稱來反映每個系列所代表的資料。

#### Q3。什麼是圖表系列平滑？
圖表系列平滑是一種視覺增強技術，可讓您建立連接圖表上的點的平滑線。它應用平滑演算法（例如 Catmull-Rom 樣條線）在數據點之間進行插值並創建視覺上令人愉悅的曲線。要使用 Aspose.Words for .NET 在圖表中啟用系列平滑，請訪問`Smooth`的財產`ChartSeries`對象並將其設定為`true`。平滑可用於顯示具有不規則波動的資料的趨勢或模式。

#### Q4。如何為圖表系列中的資料點自訂標記？
要使用 Aspose.Words for .NET 自訂圖表系列中資料點的標記，您需要存取`Marker`的財產`ChartSeries`物件並修改其屬性，例如`Symbol`和`Size`。標記是放置在圖表上的視覺指示器，用於表示各個數據點。您可以從各種內建標記符號中進行選擇，並調整其大小以突出顯示或區分系列中的特定資料點。

#### Q5.我可以反轉圖表系列中負值的顏色嗎？
是的，您可以使用 Aspose.Words for .NET 反轉圖表系列中負值的顏色。透過設定`InvertIfNegative`的財產`ChartSeries`反對`true`，具有負值的資料點的顏色將被反轉，使它們在視覺上與正值不同。在比較圖表系列中的正值和負值時，此功能非常有用，可以清楚地區分兩者。