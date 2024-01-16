---
title: 在 Word 文件中插入長條圖
linktitle: 在 Word 文件中插入長條圖
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將長條圖插入文件中。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/insert-column-chart/
---

本教學介紹如何使用 Aspose.Words for .NET 將長條圖插入文件中。提供的原始程式碼示範如何建立圖表、新增系列資料以及儲存文件。

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

接下來，使用`InsertChart`的方法`DocumentBuilder`將長條圖插入文件中。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 步驟 3：將系列資料加入圖表中

將系列資料新增至圖表。在此範例中，我們將新增兩個類別及其對應的值。

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## 步驟 4：儲存文檔

最後，使用命令將文檔儲存到指定目錄`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

這樣就完成了使用Aspose.Words for .NET插入長條圖的實作。

### 使用 Aspose.Words for .NET 插入長條圖的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

## 結論

在本教學中，您學習如何使用 Aspose.Words for .NET 將長條圖插入 Word 文件中。透過遵循逐步指南並使用提供的原始程式碼，您可以建立新文件、插入長條圖、新增系列資料以及使用圖表儲存文件。

Aspose.Words for .NET 為 Word 文件中的圖表進行文字處理提供了強大的 API。長條圖通常用於顯示和比較不同類別或組別的數據。透過 Aspose.Words for .NET，您可以輕鬆建立長條圖，有效地視覺化您的資料並提供有價值的見解。

透過使用 Aspose.Words for .NET，您可以自動產生具有長條圖的文件的過程，從而節省手動文件建立的時間和精力。該庫提供了廣泛的圖表類型和自訂選項，可讓您在 Word 文件中建立具有視覺吸引力且資料豐富的圖表。

### 常見問題解答

#### Q1.什麼是長條圖？
長條圖是一種以垂直長條或長條表示資料的圖表類型。每個欄位通常代表一個類別或群組，並且列的高度或長度指示與該類別關聯的資料的值。長條圖通常用於比較不同類別的數據或追蹤隨時間的變化。

#### Q2。我可以為長條圖添加多個系列嗎？
是的，您可以使用 Aspose.Words for .NET 將多個系列新增至長條圖中。每個系列代表一組資料點及其各自的類別和值。透過新增多個系列，您可以在同一圖表中比較和分析不同的資料集，從而提供資料的全面視圖。

#### Q3。我可以自訂長條圖的外觀嗎？
是的，使用 Aspose.Words for .NET，您可以自訂長條圖外觀的各個方面。您可以修改系列顏色、軸標籤、列寬和圖表區域格式等屬性。該庫提供了一組豐富的 API 來控制圖表的視覺元素並創建適合您需求的自訂外觀。

#### Q4。我可以將插入長條圖的文件儲存為不同格式嗎？
是的，Aspose.Words for .NET 允許您以各種格式儲存插入長條圖的文檔，例如 DOCX、PDF、HTML 等。您可以根據您的要求選擇所需的輸出格式並使用`Save`的方法`Document`對象來保存文檔。插入的長條圖將保留在已儲存的文件中。

#### Q5.插入長條圖後可以修改其資料和外觀嗎？
是的，將長條圖插入文件後，您可以使用 Aspose.Words for .NET 提供的 API 修改其資料和外觀。您可以更新系列資料、變更列顏色、自訂軸屬性以及套用格式選項以在 Word 文件中建立動態和互動式圖表。