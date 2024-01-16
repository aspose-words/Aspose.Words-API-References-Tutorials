---
title: 直接插入表格
linktitle: 直接插入表格
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將表格直接插入 Word 文件中。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/insert-table-directly/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 將表格直接插入 Word 文件中。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠以程式設計方式將表格直接插入 Word 文件中。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 步驟2：建立文件和表格
要使用陣列啟動文字處理，我們需要建立一個新文件並初始化陣列。按著這些次序：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文件創建
Document doc = new Document();

//建立數組
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 第 3 步：建構陣列
接下來，我們將透過新增行和單元格來建立表格。使用以下程式碼為例：

```csharp
//建立第一行
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

//建立第一個單元格
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

//複製該單元格作為行中的第二個單元格
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

這裡我們建立一行`AllowBreakAcrossPages`屬性設定為`true`允許行之間分頁。然後，我們建立一個具有彩色背景、固定寬度和指定文字內容的儲存格。然後，我們複製該單元格以建立該行中的第二個單元格。

## 第 4 步：自動調整表格
我們可以對表格套用自動調整以正確設定其格式。使用以下程式碼：

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

這行程式碼應用基於固定列寬的自動調整。

## 第 5 步：註冊

  修改後的文件
最後，我們需要將修改後的文件與直接插入的表格一起儲存。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。

### 使用 Aspose.Words for .NET 直接插入表格的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	//我們首先建立表物件。注意我們必須傳遞文檔對象
	//到每個節點的構造函數。這是因為我們創建的每個節點都必須屬於
	//到某個文檔。
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	//在這裡，我們可以呼叫 EnsureMinimum 為我們建立行和單元格。使用這個方法
	//確保指定的節點有效。在這種情況下，有效的表格應至少具有一行和一個儲存格。
	//相反，我們將自己處理創建行和表。
	//如果我們在演算法中建立表，這將是最好的方法。
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	//我們現在可以套用任何自動調整設定。
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	//然後，我們將對錶中的其他單元格和行重複該過程。
	//我們還可以透過複製現有的單元格和行來加快速度。
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 將表格直接插入 Word 文件中。透過遵循本逐步指南並實現提供的 C# 程式碼，您可以透過程式設計方式將表格直接插入 Word 文件中。此功能可讓您根據您的特定需求建立和自訂表格。