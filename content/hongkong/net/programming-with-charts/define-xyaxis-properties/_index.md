---
title: 在圖表中定義 XY 軸屬性
linktitle: 在圖表中定義 XY 軸屬性
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在圖表中定義 XY 軸屬性。演示了 X 軸和 Y 軸的定制選項。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/define-xyaxis-properties/
---

本教學介紹如何使用 Aspose.Words for .NET 定義圖表中 X 軸和 Y 軸的屬性。提供的原始程式碼示範如何建立圖表、新增系列資料以及自訂軸屬性。

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

接下來，使用以下命令將圖表插入到文件中`InsertChart`的方法`DocumentBuilder`。在此範例中，我們將插入面積圖。

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## 步驟 3：將系列資料加入圖表中

將系列資料新增至圖表。在此範例中，我們將新增五個資料點以及相應的日期和值。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## 第 4 步：自訂 X 和 Y 軸屬性

若要自訂 X 軸和 Y 軸的屬性，請造訪`ChartAxis`與圖表關聯的物件。

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

修改屬性`xAxis`和`yAxis`物件來設定 X 軸和 Y 軸所需的選項。在此範例中，我們將示範一些可以自訂的常見屬性。

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## 第 5 步：儲存文檔

最後，使用命令將文檔儲存到指定目錄`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

這樣就完成了使用 Aspose.Words for .NET 在圖表中定義 XY 軸屬性的實作。

### 使用 Aspose.Words for .NET 定義 XYAxis 屬性的範例原始碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//插入圖表
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	//將 X 軸更改為類別而不是日期，這樣所有的點將在 X 軸上等間隔放置。
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //以 Y 軸的顯示單位（百）測量。
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## 結論

在本教學中，您學習如何使用 Aspose.Words for .NET 定義圖表中 X 軸和 Y 軸的屬性。透過遵循逐步指南，您可以建立圖表、新增系列資料並自訂軸屬性以滿足您的特定要求。 Aspose.Words for .NET 為 Word 文件中的圖表進行文字處理提供了全面的 API，讓您可以操作圖表的各個方面，包括軸。

透過訪問`ChartAxis`與圖表關聯的對象，您可以修改屬性，例如類別類型、軸交叉、刻度線、標籤位置、縮放比例等。這種靈活性使您能夠定製圖表軸的外觀和行為，以有效地呈現您的資料。

透過使用 Aspose.Words for .NET，您可以將圖表建立和自訂功能無縫整合到您的 .NET 應用程式中，並自動產生具有豐富視覺化效果的專業文件。

### 常見問題解答

#### Q1.什麼是 Aspose.Words for .NET？
Aspose.Words for .NET 是一個功能強大的文件處理庫，使開發人員能夠在 .NET 應用程式中以程式設計方式建立、操作和保存 Word 文件。它為文檔元素（包括圖表）的文字處理提供了廣泛的功能。

#### Q2。如何安裝 Aspose.Words for .NET？
您可以使用 Visual Studio 中的 NuGet 套件管理器下載 Aspose.Words for .NET 來安裝它。只需在 NuGet 套件管理器中搜尋“Aspose.Words”並將其安裝到您的專案中即可。

#### Q3。我可以使用 Aspose.Words for .NET 自訂圖表的其他方面嗎？
是的，Aspose.Words for .NET 提供了廣泛的功能來自訂圖表的各個方面。除了定義軸屬性之外，您還可以修改圖表類型、資料系列、圖例、標題、繪圖區域、資料標籤和圖表的許多其他元素。此 API 提供對圖表外觀和行為的細粒度控制。

#### Q4。我可以使用 Aspose.Words for .NET 建立不同類型的圖表嗎？
是的，Aspose.Words for .NET 支援多種圖表類型，包括面積圖、長條圖、折線圖、圓餅圖、散佈圖等。您可以使用`ChartType`枚舉以在將圖表形狀插入 Word 文件時指定所需的圖表類型。

#### Q5.我可以以不同的格式儲存圖表嗎？
是的，Aspose.Words for .NET 允許您以各種格式儲存包含圖表的文檔，例如 DOCX、PDF、HTML 等。您可以根據您的要求選擇合適的格式並使用`Save`的方法`Document`對象來保存文檔。

#### Q6.我可以將這些技術應用於文件中的多個圖表嗎？
是的，您可以透過對每個圖表重複必要的步驟，將這些技術套用到文件中的多個圖表。您可以建立單獨的`Chart`和`ChartAxis`每個圖表的物件並相應地自訂其屬性。 Aspose.Words for .NET 提供單一文件中多個圖表的文字處理的全面支援。