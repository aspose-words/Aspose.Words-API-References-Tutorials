---
title: 設定圖表中資料標籤數量的格式
linktitle: 設定圖表中資料標籤數量的格式
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 設定圖表中資料標籤數量的格式。輕鬆自訂資料標籤的數字格式。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/format-number-of-data-label/
---

本教學介紹如何使用 Aspose.Words for .NET 設定圖表中資料標籤數量的格式。提供的原始程式碼示範如何建立圖表、新增系列資料以及自訂資料標籤的數字格式。

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

接下來，使用以下命令將圖表插入到文件中`InsertChart`的方法`DocumentBuilder`。在此範例中，我們將插入折線圖。

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## 步驟 3：將系列資料加入圖表中

將系列資料新增至圖表。在此範例中，我們將新增三個類別及其對應的值。

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## 步驟4：自訂資料標籤的數字格式

要格式化資料標籤的數量，請訪問`DataLabels`與該系列相關的收藏。

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

在此範例中，我們為每個資料標籤設定不同的數字格式。第一個資料標籤的格式為貨幣，第二個資料標籤的格式為日期，第三個資料標籤的格式為百分比。

## 第 5 步：儲存文檔

最後，使用命令將文檔儲存到指定目錄`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

這樣就完成了使用 Aspose.Words for .NET 對圖表中資料標籤數量進行格式化的實作。

### 使用 Aspose.Words for .NET 設定資料標籤數量格式的範例原始碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	//刪除預設產生的系列。
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	//或者您可以設定連結到來源單元格的格式代碼，
	//在這種情況下，NumberFormat 將重設為常規並從來源單元格繼承。
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## 結論

在本教學中，您學習如何使用 Aspose.Words for .NET 設定圖表中資料標籤數量的格式。透過遵循逐步指南並使用提供的原始程式碼，您可以建立圖表、新增系列資料並根據您的要求自訂資料標籤的數字格式。

 Aspose.Words for .NET 為 Word 文件中的圖表進行文字處理提供了全面的 API，讓您可以操作圖表的各個方面，包括資料標籤。透過訪問`DataLabels`與系列關聯的集合，您可以自訂各個資料標籤的數字格式。

此 API 可讓您控制值的顯示，為每個資料標籤設定不同的數字格式，並將數字格式連結到來源儲存格。這種靈活性使您能夠以所需的格式（例如貨幣符號、日期格式和百分比值）在圖表中顯示數字資料。

透過使用 Aspose.Words for .NET，您可以將強大的圖表功能合併到您的 .NET 應用程式中，並產生具有完全格式化的圖表和資料標籤的具有專業外觀的文件。

### 常見問題解答

#### Q1.什麼是 Aspose.Words for .NET？
Aspose.Words for .NET 是一個功能豐富的文件處理庫，使開發人員能夠在 .NET 應用程式中以程式設計方式建立、操作和儲存 Word 文件。它為文件元素（包括圖表和資料標籤）的文字處理提供了廣泛的功能。

#### Q2。如何安裝 Aspose.Words for .NET？
您可以使用 Visual Studio 中的 NuGet 套件管理器下載 Aspose.Words for .NET 來安裝它。只需在 NuGet 套件管理器中搜尋“Apose.Words”並將其安裝到您的專案中即可。

#### Q3。我可以使用 Aspose.Words for .NET 格式化圖表的其他方面嗎？
是的，Aspose.Words for .NET 提供了格式化圖表各個方面的廣泛功能。除了資料標籤之外，您還可以自訂圖表類型、系列資料、軸屬性、圖例、標題、繪圖區域以及圖表的許多其他元素。此 API 提供對圖表外觀和格式的細粒度控制。

#### Q4。我可以對同一系列的不同資料標籤套用不同的數字格式嗎？
是的，Aspose.Words for .NET 可讓您將不同的數位格式套用到同一系列中的各個資料標籤。透過訪問`DataLabels`與系列關聯的集合，您可以設定`FormatCode`每個資料標籤的屬性來指定所需的數字格式。這允許您在同一圖表中以不同格式呈現數值。

#### Q5.我可以對資料標籤使用自訂數字格式嗎？
是的，Aspose.Words for .NET 支援資料標籤的自訂數字格式。您可以透過設定指定所需的數字格式`FormatCode`資料標籤的屬性到自訂格式代碼。這使您可以靈活地應用各種數字格式，例如貨幣符號、日期格式、百分比值等。

#### Q6.我可以用不同格式儲存帶有格式化資料標籤的圖表嗎？
是的，Aspose.Words for .NET 允許您以各種格式（例如 DOCX、PDF、HTML 等）儲存包含具有格式化資料標籤的圖表的文件。您可以根據您的要求選擇合適的格式並使用`Save`的方法`Document`對象來保存文檔。格式化的資料標籤將保留在已儲存的文件中。