---
title: 在Word文件中插入氣泡圖
linktitle: 在Word文件中插入氣泡圖
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將氣泡圖插入文件中。新增具有 X、Y 和氣泡大小值的系列資料。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/insert-bubble-chart/
---

本教學介紹如何使用 Aspose.Words for .NET 將氣泡圖插入文件中。提供的原始程式碼示範如何建立圖表、新增系列資料以及儲存文件。

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

接下來，使用`InsertChart`的方法`DocumentBuilder`將氣泡圖插入文件中。

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## 步驟 3：將系列資料加入圖表中

將系列資料新增至圖表。在此範例中，我們將新增三個資料點以及對應的 X、Y 和氣泡大小值。

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## 步驟 4：儲存文檔

最後，使用命令將文檔儲存到指定目錄`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

這樣就完成了使用Aspose.Words for .NET插入氣泡圖的實作。

### 使用 Aspose.Words for .NET 插入氣泡圖的範例原始程式碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

## 結論

在本教學中，您學習如何使用 Aspose.Words for .NET 將氣泡圖插入 Word 文件中。透過遵循逐步指南並使用提供的原始程式碼，您可以建立新文件、插入氣泡圖、新增系列資料以及使用圖表儲存文件。

Aspose.Words for .NET 為 Word 文件中的圖表進行文字處理提供了強大的 API。氣泡圖非常適合視覺化三維數據，其中每個數據點都由帶有 X 和 Y 座標以及大小值的氣泡表示。透過 Aspose.Words for .NET，您可以建立動態且資訊豐富的氣泡圖，從而增強資料的視覺化表示。

透過使用 Aspose.Words for .NET，您可以自動化產生帶有氣泡圖的文件的過程，從而節省手動文件建立的時間和精力。該庫提供了廣泛的圖表類型和自訂選項，可讓您在 Word 文件中建立具有視覺吸引力且資料豐富的圖表。

### 常見問題解答

#### Q1.什麼是氣泡圖？
氣泡圖是一種使用氣泡或球體顯示三維資料的圖表。每個數據點都由一個氣泡表示，其中 X 和 Y 座標決定氣泡在圖表上的位置，氣泡的大小表示資料的第三個維度。氣泡圖對於可視化多個變數之間的關係和模式很有用。

#### Q2。我可以為氣泡圖添加多個系列嗎？
是的，您可以使用 Aspose.Words for .NET 將多個系列新增至氣泡圖中。每個系列代表一組資料點及其各自的 X、Y 和氣泡大小值。透過新增多個系列，您可以在同一圖表中比較和分析不同的資料集，從而提供資料的全面視圖。

#### Q3。我可以自訂氣泡圖的外觀嗎？
是的，使用 Aspose.Words for .NET，您可以自訂氣泡圖外觀的各個方面。您可以修改系列顏色、氣泡大小、軸標籤和圖表區域格式等屬性。該庫提供了一組豐富的 API 來控制圖表的視覺元素並創建適合您需求的自訂外觀。

#### Q4。我可以將插入氣泡圖的文件儲存為不同格式嗎？
是的，Aspose.Words for .NET 允許您以各種格式儲存插入氣泡圖的文檔，例如 DOCX、PDF、HTML 等。您可以根據您的要求選擇所需的輸出格式並使用`Save`的方法`Document`對象來保存文檔。插入的氣泡圖將保留在已儲存的文件中。

#### Q5.插入氣泡圖後可以修改其數據和外觀嗎？
是的，將氣泡圖插入文件後，您可以使用 Aspose.Words for .NET 提供的 API 修改其資料和外觀。您可以更新系列資料、變更氣泡大小、自訂軸屬性以及套用格式選項以在 Word 文件中建立動態和互動式圖表。