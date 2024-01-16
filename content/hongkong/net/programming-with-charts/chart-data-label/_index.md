---
title: 自訂圖表資料標籤
linktitle: 自訂圖表資料標籤
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在圖表中新增和自訂資料標籤，以提供有關資料點的附加資訊。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/chart-data-label/
---

本教學介紹如何使用 Aspose.Words for .NET 在圖表中新增和自訂資料標籤。數據標籤提供有關圖表中數據點的附加資訊。

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
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## 第 4 步：自訂資料標籤
存取圖表系列的資料標籤集合併修改各種屬性以自訂資料標籤的外觀。

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## 第 5 步：儲存文檔
使用以下命令將文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithCharts.ChartDataLabel.docx」。

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### 使用 Aspose.Words for .NET 的圖表資料標籤的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	//預設情況下，當您在圓餅圖中的資料點新增資料標籤時，會顯示下列資料標籤的引導線：
	//位於遠離資料點末端的位置。引導線在資料標籤及其內容之間創建視覺連接
	//對應的數據點。
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 在圖表中成功新增和自訂資料標籤。

## 結論
在本教學中，您學習如何使用 Aspose.Words for .NET 在圖表中新增和自訂資料標籤。透過遵循逐步指南，您可以插入圖表、存取資料標籤集合以及修改屬性以自訂資料標籤的外觀。 Aspose.Words for .NET 提供了強大的 API，用於 Word 文件和圖表的文字處理，使您能夠使用自訂資料標籤建立具有視覺吸引力和資訊豐富的圖表。

### 常見問題解答

#### Q1.圖表中的數據標籤是什麼？
圖表中的資料標籤提供有關圖表中表示的資料點的附加資訊。它們可以根據圖表類型和配置顯示值、類別、系列名稱、百分比或其他相關詳細資訊。

#### Q2。我可以自訂資料標籤的外觀嗎？
是的，您可以自訂圖表中資料標籤的外觀。 Aspose.Words for .NET 提供了修改資料標籤各種屬性的選項，例如顯示圖例鍵、引導線、類別名稱、系列名稱、值等。您也可以設定分隔符號並設定標籤格式以滿足您的特定要求。

#### Q3。我可以將資料標籤新增到任何圖表類型嗎？
是的，您可以為各種類型的圖表新增資料標籤，包括長條圖、圓餅圖、折線圖等。新增和自訂資料標籤的過程可能會略有不同，具體取決於圖表類型以及您正在使用的程式庫或工具。
