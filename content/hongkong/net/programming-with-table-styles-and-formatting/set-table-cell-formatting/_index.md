---
title: 設定表格單元格格式
linktitle: 設定表格單元格格式
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 設定表格儲存格格式的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-table-styles-and-formatting/set-table-cell-formatting/
---

在本教程中，我們將引導您完成使用 Aspose.Words for .NET 定義表格單元格格式的逐步過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何使用 Aspose.Words for .NET 調整 Word 文件表格中儲存格的寬度和邊距（填滿）。

## 步驟1：定義文檔目錄
首先，您需要設定文檔目錄的路徑。這是您要儲存編輯的 Word 文件的位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟 2：建立新文檔和文檔產生器
接下來，您需要建立一個新的實例`Document`類別和該文檔的文檔建構子。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：建立一個新表格並新增一個儲存格
要開始建立表，我們使用`StartTable()`文檔建構函數的方法，然後我們使用`InsertCell()`方法。

```csharp
builder. StartTable();
builder. InsertCell();
```

## 步驟 4：設定儲存格格式
現在我們可以透過存取來設定儲存格格式`CellFormat`的對象`DocumentBuilder`目的。我們可以使用對應的屬性來設定單元格寬度和邊距（填滿）。

```csharp
CellFormat cellFormat = builder. CellFormat;
cellFormat. Width = 250;
cellFormat. LeftPadding = 30;
cellFormat. RightPadding = 30;
cellFormat. TopPadding = 30;
cellFormat.BottomPadding = 30;
```

## 步驟 5：為儲存格新增內容
然後我們可以使用文檔產生器向單元格添加內容`Writeln()`方法。

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## 步驟 6：完成表格並儲存文檔
最後，我們使用以下命令完成表格的創建`EndRow()`方法和`EndTable()`，然後我們將修改後的文件儲存到文件中。

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

### 使用 Aspose.Words for .NET 設定表格儲存格格式的範例原始碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	CellFormat cellFormat = builder.CellFormat;
	cellFormat.Width = 250;
	cellFormat.LeftPadding = 30;
	cellFormat.RightPadding = 30;
	cellFormat.TopPadding = 30;
	cellFormat.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 設定表格儲存格的格式。透過遵循此逐步指南，您可以輕鬆調整 Word 文件表格中儲存格的寬度和邊距。 Aspose.Words 提供了強大且靈活的 API，用於操作文件中的表格並設定其格式。有了這些知識，您就可以根據您的特定需求自訂表格的視覺佈局。