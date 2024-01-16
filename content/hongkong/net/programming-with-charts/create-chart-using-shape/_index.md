---
title: 使用形狀建立和自訂圖表
linktitle: 使用形狀建立和自訂圖表
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 使用 Word 文件中的形狀建立和自訂圖表。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/create-chart-using-shape/
---

本教學課程說明如何使用 Aspose.Words for .NET 使用 Word 文件中的形狀建立圖表。

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

## 步驟 3：插入並配置圖表形狀
使用以下命令將圖表形狀插入到文件中`InsertChart`的方法`DocumentBuilder`目的。設定所需的圖表類型和尺寸。

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 第 4 步：自訂圖表
透過修改圖表標題和圖例等各種屬性來自訂圖表。

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## 第 5 步：儲存文檔
使用以下命令將文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithCharts.CreateChartUsingShape.docx」。

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### 使用 Aspose.Words for .NET 使用形狀建立圖表的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	//請注意，如果將 null 或空值指定為標題文本，則會顯示自動產生的標題。
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 使用 Word 文件中的形狀成功建立了圖表。

## 結論
在本教學中，您學習如何使用 Aspose.Words for .NET 使用 Word 文件中的形狀建立圖表。透過遵循逐步指南，您可以插入和配置圖表形狀、自訂其外觀並儲存文件。 Aspose.Words for .NET 提供了一套全面的 Word 文件和圖表文字處理功能，使您能夠直接在 .NET 應用程式中建立具有專業外觀和視覺吸引力的圖表。

### 常見問題解答

#### Q1.我可以使用 Aspose.Words for .NET 在 Word 文件中建立圖表嗎？
是的，使用 Aspose.Words for .NET，您可以以程式設計方式在 Word 文件中建立圖表。 Aspose.Words 提供 API 和功能來插入各種類型的圖表、自訂其外觀以及操作圖表資料。

#### Q2。 Aspose.Words for .NET 支援哪些圖表類型？
Aspose.Words for .NET 支援多種圖表類型，包括折線圖、長條圖、圓餅圖、面積圖、散佈圖等。您可以根據您的資料和視覺化需求選擇合適的圖表類型。

#### Q3。我可以自訂創建的圖表的外觀嗎？
是的，您可以使用 Aspose.Words for .NET 自訂建立的圖表的外觀。您可以修改圖表標題、圖例位置、資料標籤、軸標籤、顏色和其他視覺元素等屬性，以滿足您的特定設計和格式設定需求。
