---
title: 首選寬度設定
linktitle: 首選寬度設定
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中設定首選表格儲存格寬度。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/preferred-width-settings/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 設定 Word 文件中表格儲存格的首選寬度設定。我們將按照逐步指南來理解程式碼並實現此功能。在本教學課程結束時，您將能夠為 Word 文件中的表格儲存格指定不同的首選寬度。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 步驟2：建立文件並初始化文檔產生器
若要使用文件和文件產生器啟動字處理，請依照下列步驟操作：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文件創建
Document doc = new Document();

//初始化文檔產生器
DocumentBuilder builder = new DocumentBuilder(doc);
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 第 3 步：建立具有首選寬度的表格
接下來，我們將建立一個包含三個具有不同首選寬度的單元格的表格。使用以下程式碼：

```csharp
//表的開頭
builder. StartTable();

//插入絕對大小的儲存格
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

//插入相對大小的儲存格（以百分比表示）
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

//插入自動調整大小的儲存格
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

//表尾
builder. EndTable();
```

這裡我們使用文件產生器來建立一個包含三個單元格的表格。第一個單元格的首選寬度為 40 磅，第二個單元格的首選寬度為表格寬度的 20%，第三個單元格的首選寬度可自動調整

  取決於可用空間。

## 第四步：儲存修改後的文檔
最後，我們需要使用表格儲存格定義的首選寬度設定來儲存修改後的文件。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。

### 使用 Aspose.Words for .NET 的首選寬度設定的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//插入由三個具有不同首選寬度的單元格組成的表格行。
	builder.StartTable();
	//插入絕對大小的儲存格。
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	//插入相對（百分比）大小的儲存格。
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	//插入自動調整大小的儲存格。
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 設定 Word 文件中表格儲存格的首選寬度設定。透過遵循本逐步指南並實施提供的 C# 程式碼，您可以根據您在 Word 文件中的特定需求自訂表格儲存格寬度。