---
title: 自訂圖表中的單一圖表資料點
linktitle: 自訂圖表中的單一圖表資料點
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 自訂圖表中的單一資料點。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/single-chart-data-point/
---

本教學介紹如何使用 Aspose.Words for .NET 自訂圖表中的單一資料點。提供的原始程式碼示範如何建立圖表、存取特定資料點以及修改其屬性。

## 第 1 步：設定項目

確保您具備以下先決條件：

- 已安裝 Aspose.Words for .NET 程式庫。您可以使用 NuGet 套件管理員下載並安裝它。
- 將儲存輸出文檔的文檔目錄路徑。

## 步驟2：建立一個新文件並插入圖表。

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

## 第 3 步：存取和自訂資料點

要修改單一數據點，您需要訪問`ChartDataPointCollection`系列並使用索引選擇所需的資料點。

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## 步驟 4：儲存文檔

最後，使用命令將文檔儲存到指定目錄`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

這樣就完成了使用 Aspose.Words for .NET 自訂圖表中單一資料點的實作。

### 使用 Aspose.Words for .NET 的單一圖表資料點的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## 結論

在本教學中，您學習如何使用 Aspose.Words for .NET 自訂圖表中的單一資料點。透過遵循逐步指南並利用提供的原始程式碼，您可以建立新文件、插入折線圖、存取圖表系列中的特定資料點以及修改其屬性以實現所需的自訂。

Aspose.Words for .NET 提供了強大的功能來操作 Word 文件中的圖表。透過存取圖表系列中的各個數據點，您可以套用特定的修改來自訂其外觀和行為。這使您可以突出顯示特定資料點、更改標記符號、調整標記大小等，以增強圖表的視覺表示。

自訂各個數據點可讓您靈活地強調重要數據或突出顯示圖表中的特定趨勢。透過 Aspose.Words for .NET，您可以輕鬆存取和修改各種圖表類型中的資料點，從而使您能夠在 Word 文件中建立具有視覺吸引力且資訊豐富的圖表。

### 常見問題解答

#### Q1.我可以在圖表中自訂多個數據點嗎？
是的，您可以使用 Aspose.Words for .NET 自訂圖表中的多個資料點。透過訪問`ChartDataPointCollection`在一個系列中，您可以根據其索引選擇和修改多個資料點。使用循環或單獨指派來修改每個資料點所需的屬性。這樣，您可以將不同的自訂套用到同一圖表中的多個資料點。

#### Q2。如何更改資料點的標記符號？
要使用 Aspose.Words for .NET 更改圖表中資料點的標記符號，您需要訪問`Marker`的財產`ChartDataPoint`對象並設定`Symbol`屬性到所需的標記符號。標記符號代表用於表示圖表上每個資料點的形狀或圖示。您可以從各種內建標記符號中進行選擇，例如圓形、方形、菱形、三角形、星形等。

#### Q3。我可以調整資料點標記的大小嗎？
是的，您可以使用 Aspose.Words for .NET 調整圖表中資料點標記的大小。訪問`Marker`的財產`ChartDataPoint`對象並設定`Size`屬性到所需的標記大小。標記的大小通常以點為單位指定，其中較大的值表示較大的標記大小。調整標記大小可以讓您強調特定資料點或根據其重要性區分它們。

#### Q4。我還可以修改資料點的哪些其他屬性？
Aspose.Words for .NET 提供了一系列可以修改圖表中資料點的屬性。一些常見修改的屬性包括標記符號、標記大小、標記顏色、資料標籤可見性、爆炸、反轉（如果為負）等等。這些屬性可讓您自訂各個資料點的外觀、行為和互動性，使您能夠建立適合您的特定要求的圖表。

#### Q5.我可以自訂其他圖表類型中的資料點嗎？
是的，您可以使用 Aspose.Words for .NET 自訂各種圖表類型中的資料點。雖然本教學示範如何自訂折線圖中的資料點，但您可以將類似的技術應用於其他圖表類型，例如長條圖、長條圖、圓餅圖等。這個過程涉及存取圖表中的系列和資料點並相應地修改它們的屬性。