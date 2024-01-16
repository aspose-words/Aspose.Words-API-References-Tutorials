---
title: 在 Word 文件中隱藏圖表軸
linktitle: 在 Word 文件中隱藏圖表軸
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在文件中隱藏圖表軸。隱藏軸以獲得更清晰、更集中的圖表顯示。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/hide-chart-axis/
---

本教學介紹如何使用 Aspose.Words for .NET 隱藏文件中的圖表軸。提供的原始程式碼示範如何建立圖表、新增系列資料以及隱藏圖表軸。

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

接下來，使用以下命令將圖表插入到文件中`InsertChart`的方法`DocumentBuilder`。在此範例中，我們將插入長條圖。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 步驟 3：將系列資料加入圖表中

將系列資料新增至圖表。在此範例中，我們將新增五個項目及其對應的值。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 步驟 4：隱藏圖表軸

若要隱藏圖表軸，請訪問`AxisY`圖表的屬性並設定`Hidden`財產給`true`.

```csharp
chart.AxisY.Hidden = true;
```

在此範例中，我們隱藏圖表的 Y 軸。

## 第 5 步：儲存文檔

最後，使用命令將文檔儲存到指定目錄`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

這樣就完成了使用Aspose.Words for .NET隱藏圖表軸的實作。

### 使用 Aspose.Words for .NET 隱藏圖表軸的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## 結論

在本教學中，您學習如何使用 Aspose.Words for .NET 在 Word 文件中隱藏圖表軸。透過遵循逐步指南並使用提供的原始程式碼，您可以建立圖表、新增系列資料並隱藏圖表軸以實現所需的視覺效果。

 Aspose.Words for .NET 為 Word 文件中的圖表進行文字處理提供了全面的 API，讓您可以操作圖表的各個方面，包括軸屬性。透過訪問`AxisY`在圖表屬性中，您可以隱藏 Y 軸以將其從圖表視覺化中刪除。

當您想要專注於圖表資料而不被軸線和標籤分散注意力時，隱藏圖表軸會很有用。它為圖表提供了更乾淨、更簡約的外觀。

透過使用 Aspose.Words for .NET，您可以輕鬆地將圖表功能合併到您的 .NET 應用程式中，並產生具有自訂圖表和隱藏圖表軸的具有專業外觀的文件。

### 常見問題解答

#### Q1.什麼是 Aspose.Words for .NET？
Aspose.Words for .NET 是一個功能強大的文件處理庫，使開發人員能夠在 .NET 應用程式中以程式設計方式建立、操作和保存 Word 文件。它為文檔元素（包括圖表和圖表軸）的文字處理提供了廣泛的功能。

#### Q2。如何安裝 Aspose.Words for .NET？
您可以使用 Visual Studio 中的 NuGet 套件管理器下載 Aspose.Words for .NET 來安裝它。只需在 NuGet 套件管理器中搜尋“Aspose.Words”並將其安裝到您的專案中即可。

#### Q3。我可以隱藏圖表的 X 軸和 Y 軸嗎？
是的，您可以使用 Aspose.Words for .NET 隱藏圖表的 X 軸和 Y 軸。要隱藏 X 軸，您可以訪問`AxisX`圖表的屬性並設定`Hidden`財產給`true`。同樣，要隱藏 Y 軸，您可以訪問`AxisY`屬性並設定`Hidden`財產給`true`。這允許您從圖表視覺化中刪除兩個軸。

#### Q4。隱藏軸後可以再次顯示嗎？
是的，您可以使用 Aspose.Words for .NET 隱藏圖表軸後再次顯示它。若要顯示隱藏軸，只需設定`Hidden`對應的屬性`AxisX`或者`AxisY`反對`false`。這將使軸在圖表中再次可見。

#### Q5.我可以自訂圖表軸的其他屬性嗎？
是的，Aspose.Words for .NET 可讓您自訂圖表軸的各種屬性，例如軸標題、標籤、線條顏色等。透過訪問`AxisX`和`AxisY`圖表的屬性，您可以修改屬性，例如`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`，以及許多其他人。這使您可以對圖表軸的外觀和行為進行細微控制。

#### Q6.我可以將帶有隱藏軸的圖表儲存為不同的文件格式嗎？
是的，Aspose.Words for .NET 允許您以各種文件格式儲存包含帶有隱藏軸的圖表的文檔，例如 DOCX、PDF、HTML 等。您可以根據您的要求選擇所需的輸出格式並使用`Save`的方法`Document`對象來保存文檔。隱藏的軸將保留在已儲存的文件中。