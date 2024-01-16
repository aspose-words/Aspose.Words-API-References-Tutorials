---
title: 將面積圖插入 Word 文檔
linktitle: 將面積圖插入 Word 文檔
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將面積圖插入文件中。新增系列資料並使用圖表儲存文件。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/insert-area-chart/
---

本教學介紹如何使用 Aspose.Words for .NET 將面積圖插入文件中。提供的原始程式碼示範如何建立圖表、新增系列資料以及儲存文件。

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

接下來，使用`InsertChart`的方法`DocumentBuilder`將面積圖插入文件中。

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## 步驟 3：將系列資料加入圖表中

將系列資料新增至圖表。在此範例中，我們將新增五個資料點以及相應的日期和值。

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## 步驟 4：儲存文檔

最後，使用命令將文檔儲存到指定目錄`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

這樣就完成了使用Aspose.Words for .NET插入面積圖的實作。

### 使用 Aspose.Words for .NET 插入面積圖的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### 結論

在本教學中，您學習如何使用 Aspose.Words for .NET 將面積圖插入 Word 文件中。透過遵循逐步指南並使用提供的原始程式碼，您可以建立新文件、插入面積圖、新增系列資料以及使用圖表儲存文件。

Aspose.Words for .NET 為 Word 文件中的圖表進行文字處理提供了強大的 API。只需幾行程式碼，您就可以建立具有專業外觀的面積圖並根據您的要求進行自訂。面積圖通常用於顯示資料隨時間或類別的大小和趨勢。

透過使用 Aspose.Words for .NET，您可以自動化產生具有面積圖的文件的過程，從而節省手動文件建立的時間和精力。該庫提供了廣泛的圖表類型和自訂選項，可讓您在 Word 文件中建立具有視覺吸引力且資訊豐富的圖表。

### 常見問題解答

#### Q1.什麼是 Aspose.Words for .NET？
Aspose.Words for .NET 是一個功能強大的文件處理庫，使開發人員能夠在 .NET 應用程式中以程式設計方式建立、修改和轉換 Word 文件。它提供了一套全面的用於文字處理的 API，其中包含文件元素，包括圖表、段落、表格等。

#### Q2。如何安裝 Aspose.Words for .NET？
若要安裝 Aspose.Words for .NET，您可以使用 Visual Studio 中的 NuGet 套件管理器將程式庫直接安裝到您的專案中。只需在 NuGet 套件管理器中搜尋“Aspose.Words”並安裝該套件即可。

#### Q3。我可以自訂面積圖的外觀嗎？
是的，使用 Aspose.Words for .NET，您可以自訂面積圖外觀的各個方面。您可以修改圖表標題、系列顏色、軸標籤和圖表區域格式等屬性。該庫提供了一組豐富的 API 來控制圖表的視覺元素並創建適合您需求的自訂外觀。

#### Q4。我可以為面積圖新增多個系列嗎？
是的，您可以使用 Aspose.Words for .NET 將多個系列新增至面積圖中。每個系列代表繪製在圖表上的一組資料點。您可以新增具有不同資料集的系列，並單獨自訂每個系列，包括其名稱、資料點和外觀。

#### Q5.我可以將插入面積圖的文件儲存為不同格式嗎？
是的，Aspose.Words for .NET 允許您以各種格式儲存插入面積圖的文檔，例如 DOCX、PDF、HTML 等。您可以根據您的要求選擇所需的輸出格式並使用`Save`的方法`Document`對象來保存文檔。插入的面積圖將保留在已儲存的文件中。

#### Q6.插入面積圖後可以修改其資料和外觀嗎？
是的，將面積圖插入文件後，您可以使用 Aspose.Words for .NET 提供的 API 修改其資料和外觀。您可以更新系列資料、變更圖表類型、自訂軸屬性以及套用格式選項以在 Word 文件中建立動態和互動式圖表。