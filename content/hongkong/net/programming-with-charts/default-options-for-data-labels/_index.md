---
title: 設定圖表中資料標籤的預設選項
linktitle: 設定圖表中資料標籤的預設選項
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 設定圖表中資料標籤的預設選項。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/default-options-for-data-labels/
---

本教學介紹如何使用 Aspose.Words for .NET 設定圖表中資料標籤的預設選項。提供的程式碼示範如何使用 Aspose.Words 建立圖表、新增資料系列以及自訂資料標籤。

## 第 1 步：設定項目

在我們開始之前，請確保您符合以下要求：

- 已安裝 Aspose.Words for .NET 程式庫。您可以使用 NuGet 套件管理員下載並安裝它。
- 將儲存輸出文檔的文檔目錄路徑。

## 步驟2：建立一個新文件並插入圖表。

首先，我們創建一個新的`Document`物件和一個`DocumentBuilder`建置文檔。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

接下來，我們使用以下命令將圖表插入到文件中`InsertChart`的方法`DocumentBuilder`。在此範例中，我們將插入一個圓餅圖。

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## 步驟 3：將資料系列加入圖表中

現在，讓我們為圖表新增一個資料系列。在此範例中，我們將新增三個類別及其對應的值。

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## 第 4 步：自訂資料標籤

要自訂圖表中的資料標籤，我們需要訪問`ChartDataLabelCollection`與該系列關聯的物件。

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

然後我們可以修改它的各種屬性`labels`物件來設定資料標籤所需的選項。在此範例中，我們將啟用顯示百分比和值、停用引導線並設定自訂分隔符號。

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## 第 5 步：儲存文檔

最後，我們使用以下命令將文件儲存到指定目錄`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

這樣就完成了使用 Aspose.Words for .NET 設定圖表中資料標籤預設選項的實作。

### 使用 Aspose.Words for .NET 的資料標籤預設選項的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

## 結論

在本教學中，您學習如何使用 Aspose.Words for .NET 設定圖表中資料標籤的預設選項。透過遵循逐步指南，您可以建立圖表、新增資料系列並自訂資料標籤以滿足您的特定要求。 Aspose.Words for .NET 為 Word 文件中的圖表進行文字處理提供了強大的 API，讓您可以操作各種圖表元素並實現所需的外觀和功能。

透過設定屬性`ChartDataLabelCollection`與圖表系列關聯的對象，您可以控制資料標籤的顯示，包括顯示百分比、值、引導線和自訂分隔符號等選項。這種靈活性使您能夠有效地呈現資料並增強圖表的可視化表示。

### 常見問題解答

#### Q1.什麼是 Aspose.Words for .NET？
Aspose.Words for .NET 是一個函式庫，可讓開發人員使用 .NET 應用程式以程式設計方式建立、操作和儲存 Word 文件。它為文檔元素（包括圖表）的文字處理提供了廣泛的功能。

#### Q2。如何安裝 Aspose.Words for .NET？
您可以透過使用 Visual Studio 中的 NuGet 套件管理器下載來安裝 Aspose.Words for .NET。只需在 NuGet 套件管理器中搜尋“Apose.Words”並將其安裝到您的專案中即可。

#### Q3。我可以使用 Aspose.Words for .NET 自訂圖表的其他方面嗎？
是的，Aspose.Words for .NET 可讓您自訂圖表的各個方面，例如圖表類型、軸標籤、圖例、繪圖區域等。您可以存取和修改圖表物件的不同屬性以實現所需的外觀和行為。

#### Q4。我可以以不同的格式儲存圖表嗎？
是的，Aspose.Words for .NET 支援以各種格式儲存包含圖表的文檔，包括 DOCX、PDF、HTML 等。您可以根據您的要求選擇合適的格式並使用`Save`的方法`Document`對象來保存文檔。

#### Q5.我可以將這些技術應用於其他圖表類型嗎？
是的，本教程中描述的技術可以應用於 Aspose.Words for .NET 支援的其他圖表類型。關鍵是存取特定於您進行文字處理的圖表類型的相關物件和屬性。