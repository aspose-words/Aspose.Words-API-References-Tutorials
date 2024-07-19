---
title: 在圖表中定義 XY 軸屬性
linktitle: 在圖表中定義 XY 軸屬性
second_title: Aspose.Words 文件處理 API
description: 透過此逐步指南，了解如何使用 Aspose.Words for .NET 在圖表中定義 XY 軸屬性。非常適合 .NET 開發人員。
type: docs
weight: 10
url: /zh-hant/net/programming-with-charts/define-xyaxis-properties/
---
## 介紹

圖表是可視化數據的強大工具。當您需要使用動態圖表建立專業文件時，Aspose.Words for .NET 是一個非常寶貴的函式庫。本文將引導您完成使用 Aspose.Words for .NET 在圖表中定義 XY 軸屬性的過程，分解每個步驟以確保清晰度和易於理解。

## 先決條件

在深入編碼之前，您需要滿足一些先決條件：

1. Aspose.Words for .NET：請確定您擁有 Aspose.Words for .NET 函式庫。你可以[在這裡下載](https://releases.aspose.com/words/net/).
2. 開發環境：您需要一個整合開發環境（IDE），例如 Visual Studio。
3. .NET Framework：確保您的開發環境已設定為 .NET 開發。
4. C# 基礎知識：本指南假設您對 C# 程式設計有基本了解。

## 導入命名空間

首先，您需要在專案中匯入必要的命名空間。這可確保您可以存取建立和操作文件和圖表所需的所有類別和方法。

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

我們將把該過程分解為簡單的步驟，每個步驟都專注於定義圖表中 XY 軸屬性的特定部分。

## 第 1 步：初始化 Document 和 DocumentBuilder

首先，您需要初始化一個新文件和一個`DocumentBuilder`目的。這`DocumentBuilder`有助於將內容插入文件中。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入圖表

接下來，您將在文檔中插入圖表。在此範例中，我們將使用面積圖。您可以根據需要自訂圖表的尺寸。

```csharp
//插入圖表
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## 步驟 3：清除預設系列並新增自訂數據

預設情況下，圖表將有一些預先定義的系列。我們將清除這些並添加我們的自訂資料系列。

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

## 步驟 4：定義 X 軸屬性

現在，是時候定義 X 軸的屬性了。這包括設定類別類型、自訂軸交叉以及調整刻度線和標籤。

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3; //以 Y 軸的顯示單位（百）測量。
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;
```

## 第 5 步：定義 Y 軸屬性

同樣，您將設定 Y 軸的屬性。這包括設定刻度標籤位置、主要和次要單位、顯示單位和縮放比例。

```csharp
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## 第 6 步：儲存文檔

最後，將文件儲存到您指定的目錄中。這將產生帶有自訂圖表的 Word 文件。

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## 結論

一旦您了解了所涉及的步驟，使用 Aspose.Words for .NET 在 Word 文件中建立和自訂圖表就變得非常簡單。本指南引導您完成在圖表中定義 XY 軸屬性的過程，從初始化文件到儲存最終產品。借助這些技能，您可以建立詳細的、具有專業外觀的圖表來增強您的文件。

## 常見問題解答

### 我可以使用 Aspose.Words for .NET 建立哪些類型的圖表？
您可以建立各種類型的圖表，包括面積圖、長條圖、折線圖、圓餅圖等。

### 如何安裝 Aspose.Words for .NET？
您可以從以下位置下載 Aspose.Words for .NET[這裡](https://releases.aspose.com/words/net/)並按照提供的安裝說明進行操作。

### 我可以自訂圖表的外觀嗎？
是的，Aspose.Words for .NET 允許對圖表進行廣泛的自訂，包括顏色、字體和軸屬性。

### Aspose.Words for .NET 有沒有免費試用版？
是的，您可以獲得免費試用[這裡](https://releases.aspose.com/).

### 在哪裡可以找到更多教學和文件？
您可以在以下位置找到更多教學課程和詳細文檔[Aspose.Words for .NET 文件頁面](https://reference.aspose.com/words/net/).
