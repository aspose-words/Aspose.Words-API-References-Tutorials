---
title: 在Word文件中插入散佈圖
linktitle: 在Word文件中插入散佈圖
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將散佈圖插入文件中。新增帶有 X 和 Y 座標的系列資料。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/insert-scatter-chart/
---

本教學介紹如何使用 Aspose.Words for .NET 將散佈圖插入文件中。提供的原始程式碼示範如何建立圖表、新增系列資料以及儲存文件。

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

接下來，使用`InsertChart`的方法`DocumentBuilder`將散佈圖插入文件中。

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## 步驟 3：將系列資料加入圖表中

將系列資料新增至圖表。在此範例中，我們將新增兩組 X 和 Y 座標。

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## 步驟 4：儲存文檔

最後，使用命令將文檔儲存到指定目錄`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

這樣就完成了使用Aspose.Words for .NET插入散佈圖的實作。

### 使用 Aspose.Words for .NET 插入散佈圖的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## 結論

在本教學中，您學習如何使用 Aspose.Words for .NET 將散佈圖插入 Word 文件中。透過遵循逐步指南並使用提供的原始程式碼，您可以建立一個新文件、插入散點圖、添加具有 X 和 Y 座標的系列數據，以及使用圖表保存文件。

Aspose.Words for .NET 為 Word 文件中的圖表進行文字處理提供了全面的 API。散點圖對於視覺化和分析具有兩個數值變數的資料非常有用。使用 Aspose.Words for .NET，您可以輕鬆建立表示 X 和 Y 值之間關係的散佈圖，並識別資料中的模式或趨勢。

透過使用 Aspose.Words for .NET，您可以自動產生具有散點圖的文件的過程，從而節省手動文件建立的時間和精力。該庫提供了多種圖表類型，包括散點圖，並提供了各種自訂選項以根據您的需求自訂圖表的外觀。

### 常見問題解答

#### Q1.什麼是散點圖？
散佈圖是一種顯示兩個數值變數之間關係的圖表。它由繪製在座標網格上的一系列點組成，一個變數表示在 X 軸上，另一個變數表示在 Y 軸上。散點圖用於識別兩組數據點之間的模式、相關性或趨勢。

#### Q2。我可以為散點圖添加多個系列嗎？
是的，您可以使用 Aspose.Words for .NET 將多個系列新增至散佈圖中。每個系列代表一組資料點及其各自的 X 和 Y 座標。透過新增多個系列，您可以在同一散佈圖中比較和分析不同的資料集，從而提供資料的全面視圖。

#### Q3。我可以自訂散點圖的外觀嗎？
是的，使用 Aspose.Words for .NET，您可以自訂散點圖外觀的各個方面。您可以修改系列顏色、標記形狀、軸標籤和圖表區域格式等屬性。該庫提供了一組豐富的 API 來控制圖表的視覺元素並創建適合您需求的自訂外觀。

#### Q4。我可以將插入散佈圖的文件儲存為不同格式嗎？
是的，Aspose.Words for .NET 允許您以各種格式儲存帶有插入的散佈圖的文檔，例如 DOCX、PDF、HTML 等。您可以根據您的要求選擇所需的輸出格式並使用`Save`的方法`Document`對象來保存文檔。插入的散佈圖將保留在已儲存的文件中。

#### Q5.插入散佈圖後可以修改資料和外觀嗎？
是的，將散佈圖插入文件後，您可以使用 Aspose.Words for .NET 提供的 API 修改其資料和外觀。您可以使用新的 X 和 Y 座標更新系列資料、變更標記形狀和顏色、自訂軸屬性以及應用程式格式設定選項以在 Word 文件中建立動態和互動式圖表。