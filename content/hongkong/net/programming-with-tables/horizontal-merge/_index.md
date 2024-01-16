---
title: 水平合併
linktitle: 水平合併
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 水平合併 Word 表格中的儲存格。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/horizontal-merge/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 等級合併 Word 文件中表格中的儲存格。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠以程式設計方式水平合併 Word 表格中的儲存格。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 步驟2：建立文件並初始化文檔產生器
要開始使用表格和儲存格進行文字處理，我們需要建立一個新文件並初始化文件產生器。按著這些次序：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//建立文檔並初始化文檔產生器
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 步驟 3：透過水平合併儲存格建立表格
接下來，我們將使用 Aspose.Words for .NET 提供的屬性建立表格並套用水平儲存格合併。使用以下程式碼：

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
//該儲存格已與前一個儲存格合併，並且應該為空白。
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

這裡我們使用文檔產生器來建立表格並設定單元格水平合併屬性。我們使用`HorizontalMerge`的財產`CellFormat`物件來指定要套用於每個儲存格的水平合併的類型。使用`CellMerge.First`我們將第一個儲存格與下一個儲存格合併，同時使用`CellMerge.Previous`我們將目前儲存格與前一個儲存格合併。`CellMerge.None`指示不應合併儲存格。

## 第四步：儲存修改後的文檔
最後，我們需要儲存修改後的文檔，並水平合併儲存格。使用以下程式碼：

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。

### 使用 Aspose.Words for .NET 進行水平合併的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	//該單元格已合併到前一個單元格，並且應該為空白。
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 等級合併 Word 文件中表格中的儲存格。透過遵循本逐步指南並實現提供的 C# 程式碼，您可以以程式設計方式在 Word 表格中套用水平儲存格合併。此功能可讓您建立更複雜的表格佈局並更好地組織資料。