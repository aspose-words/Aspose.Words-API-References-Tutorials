---
title: 圖表中軸的數字格式
linktitle: 圖表中軸的數字格式
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 設定圖表中軸的數字格式。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/number-format-for-axis/
---

本教學介紹如何使用 Aspose.Words for .NET 設定圖表中軸的數字格式。提供的原始程式碼示範如何建立圖表、新增系列資料以及設定軸標籤格式。

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

接下來，使用`InsertChart`的方法`DocumentBuilder`將長條圖插入文件中。

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
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## 步驟 4：設定軸標籤格式

若要設定 Y 軸標籤的數字格式，請造訪`AxisY`圖表的屬性並設定`NumberFormat.FormatCode`屬性到所需的格式。在本例中，我們將格式設為「#,##0」以顯示帶有千位分隔符號的數字。

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## 第 5 步：儲存文檔

最後，使用命令將文檔儲存到指定目錄`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

這樣就完成了使用Aspose.Words for .NET 設定軸的數字格式的實作。

### 使用 Aspose.Words for .NET 的 Number Format For Axis 的範例原始程式碼 

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
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## 結論

在本教學中，您學習如何使用 Aspose.Words for .NET 設定圖表中軸的數字格式。透過遵循逐步指南並利用提供的原始程式碼，您可以建立新文件、插入長條圖、新增系列資料以及設定軸標籤格式以以特定格式顯示數字。

Aspose.Words for .NET 提供了強大的功能來自訂 Word 文件中圖表的外觀。透過設定軸標籤的數字格式，您可以控制數字的顯示方式，包括小數位、千位分隔符號、貨幣符號等選項。這使您能夠以清晰且有意義的方式呈現數位數據。

使用 Aspose.Words for .NET，您可以靈活地設定圖表各個方面的格式，包括軸標籤。透過設定軸的數字格式，可以確保一致性並提高圖表的可讀性，使用戶更容易解釋所表示的值。

### 常見問題解答

#### Q1.圖表中軸的數字格式是什麼？
圖表中軸的數字格式是指應用於軸上顯示的數值的格式。它允許您控制數字的顯示方式，包括小數位、千位分隔符號、貨幣符號、百分號等選項。透過設定數字格式，您可以自訂圖表中數字資料的外觀以滿足您的特定要求。

#### Q2。如何設定軸標籤的數字格式？
要使用 Aspose.Words for .NET 設定圖表中軸標籤的數字格式，您可以存取`AxisY`圖表的屬性並設定`NumberFormat.FormatCode`屬性到所需的格式代碼。格式代碼遵循標準數字格式模式的語法，並決定數字的顯示方式。例如，您可以使用「#,##0.00」顯示帶有兩位小數和千位分隔符號的數字。

#### Q3。我可以為X軸和Y軸標籤設定不同的數字格式嗎？
是的，您可以使用 Aspose.Words for .NET 為 X 軸和 Y 軸標籤設定不同的數字格式。訪問相應的軸 (`AxisX`對於 X 軸或`AxisY`對於 Y 軸）的圖表並修改`NumberFormat.FormatCode`每個軸單獨的屬性。這允許您根據您的具體要求將不同的數字格式應用於每個軸上的標籤。

#### Q4。我可以使用哪些常見的數字格式代碼？
Aspose.Words for .NET 支援多種數字格式代碼，您可以使用它們來格式化圖表中的軸標籤。一些常見的格式代碼包括：

- `0`或者`#` - 顯示沒有小數位的數字。
- `0.00`或者`#.00` - 顯示兩位小數的數字。
- `#,##0` 顯示有千位分隔符號的數字。
- `"€"0.00` - 顯示帶有歐元貨幣符號和兩位小數的數字。
- `"%"0` - 將數字顯示為百分比。

您可以找到有關號碼的更多信息[格式代碼](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/)在 Aspose.Words for .NET 的 API 參考中。

#### Q5.我可以自訂軸標籤的其他屬性嗎？
是的，Aspose.Words for .NET 提供了廣泛的屬性來自訂軸標籤的外觀和行為。除了數字格式之外，您還可以修改字體、大小、顏色、方向、對齊方式等屬性。這使您可以完全自訂軸標籤，以滿足您所需的樣式和簡報要求。