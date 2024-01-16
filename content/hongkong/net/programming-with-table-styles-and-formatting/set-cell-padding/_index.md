---
title: 設定單元格內邊距
linktitle: 設定單元格內邊距
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 設定表格儲存格邊距的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

在本教學中，我們將引導您完成使用 Aspose.Words for .NET 設定表格單元格邊距的逐步過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何使用 Aspose.Words for .NET 調整 Word 文件表格中儲存格內容的左、上、右和下邊距（空間）。

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

## 第 4 步：設定單元格邊距
現在我們可以使用以下命令設定單元格邊距`SetPaddings()`的方法`CellFormat`目的。邊距以磅為單位定義，並以左、上、右、下的順序指定。

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
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
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### 使用 Aspose.Words for .NET 設定單元格填滿的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	//設定新增到儲存格內容的左側/頂部/右側/底部的空間量（以磅為單位）。
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 設定表格儲存格的邊距。透過遵循此逐步指南，您可以輕鬆調整儲存格邊距，以便在 Word 文件表格內容的左側、頂部、右側和底部建立空格。 Aspose.Words 提供了強大且靈活的 API，用於操作文件中的表格並設定其格式。有了這些知識，您就可以根據您的特定需求自訂表格的格式。