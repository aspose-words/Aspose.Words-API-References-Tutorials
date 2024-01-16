---
title: 在Word文件中插入簡單的長條圖
linktitle: 在Word文件中插入簡單的長條圖
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將簡單的長條圖插入文件中。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/insert-simple-column-chart/
---

本教學介紹如何使用 Aspose.Words for .NET 將簡單的長條圖插入文件中。提供的原始程式碼示範如何建立圖表、新增系列資料以及儲存文件。

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

接下來，使用`InsertChart`的方法`DocumentBuilder`將長條圖插入文件中。您可以根據您的要求指定不同的圖表類型和大小。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 步驟 3：將系列資料加入圖表中

將系列資料新增至圖表。在此範例中，我們將新增多個系列，每個系列有兩個類別。

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## 步驟 4：儲存文檔

最後，使用命令將文檔儲存到指定目錄`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

這樣就完成了使用Aspose.Words for .NET插入簡單長條圖的實作。

### 使用 Aspose.Words for .NET 插入簡單長條圖的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//您可以指定不同的圖表類型和大小。
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	//刪除預設產生的系列。
	seriesColl.Clear();
	//建立類別名稱數組，在本教程中我們有兩個類別。
	string[] categories = new string[] { "Category 1", "Category 2" };
	//請注意，資料數組不能為空，且數組的大小必須相同。
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## 結論

在本教學中，您學習如何使用 Aspose.Words for .NET 將簡單的長條圖插入 Word 文件中。透過遵循逐步指南並使用提供的原始程式碼，您可以建立一個新文件、插入長條圖、新增多個包含類別和對應值的系列，並使用圖表儲存文件。

Aspose.Words for .NET 為 Word 文件中的圖表進行文字處理提供了強大且靈活的 API。簡單的長條圖是表示和比較不同類別資料的有效方法。使用 Aspose.Words for .NET，您可以輕鬆建立具有自訂資料的長條圖，新增多個系列進行視覺比較，並根據您的要求自訂圖表的外觀。

透過使用 Aspose.Words for .NET，您可以自動產生具有長條圖的文件的過程，從而節省手動文件建立的時間和精力。該庫提供了多種圖表類型，包括簡單的長條圖，並提供了各種自訂選項來自訂圖表的外觀以滿足您的需求。

### 常見問題解答

#### Q1.什麼是長條圖？
長條圖是一種使用不同高度的垂直條顯示資料的圖表類型。每個欄位代表一個類別，列的高度對應於該類別的值。長條圖通常用於比較不同類別的數據或追蹤隨時間的變化。

#### Q2。我可以為長條圖添加多個系列嗎？
是的，使用 Aspose.Words for .NET，您可以為長條圖新增多個系列。每個系列代表一組資料點及其各自的類別和值。透過新增多個系列，您可以在同一長條圖中比較和分析不同的資料集，從而提供資料的全面視圖。

#### Q3。我可以自訂長條圖的外觀嗎？
是的，Aspose.Words for .NET 可讓您自訂長條圖外觀的各個方面。您可以修改系列顏色、軸標籤、資料標籤和圖表區域格式等屬性。該庫提供了一組豐富的 API 來控制圖表的視覺元素並創建適合您需求的自訂外觀。

#### Q4。我可以將插入長條圖的文件儲存為不同格式嗎？
是的，Aspose.Words for .NET 允許您以各種格式儲存插入長條圖的文檔，例如 DOCX、PDF、HTML 等。您可以根據您的要求選擇所需的輸出格式並使用`Save`的方法`Document`對象來保存文檔。插入的長條圖將保留在已儲存的文件中。

#### Q5.插入長條圖後可以修改其資料和外觀嗎？
是的，將長條圖插入文件後，您可以使用 Aspose.Words for .NET 提供的 API 修改其資料和外觀。您可以使用新的類別和值更新系列資料、更改列的顏色和格式、自訂軸屬性以及應用各種格式選項以在 Word 文件中建立動態且具有視覺吸引力的圖表。