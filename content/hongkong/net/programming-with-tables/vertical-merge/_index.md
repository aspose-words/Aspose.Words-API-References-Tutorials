---
title: 垂直合併
linktitle: 垂直合併
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 垂直合併 Word 文件表格中的儲存格。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/vertical-merge/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 垂直合併 Word 文件中表格中的儲存格。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠垂直合併 Word 文件中表格中的儲存格。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 第 2 步：載入文檔
若要啟動文件的文字處理，請依照下列步驟操作：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//建立一個新文檔
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 步驟 3：垂直合併儲存格
接下來我們將合併表格中的垂直儲存格。使用以下程式碼：

```csharp
//插入一個儲存格
builder. InsertCell();

//將垂直合併套用至第一個儲存格
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

//插入另一個儲存格
builder. InsertCell();

//不對單元格套用垂直合併
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

//插入一個儲存格
builder. InsertCell();

//應用與前一個單元格的垂直合併
builder.CellFormat.VerticalMerge = CellMerge.Previous;

//插入另一個儲存格
builder. InsertCell();

//不對單元格套用垂直合併
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//結束表的創建
builder. EndTable();
```

在此程式碼中，我們使用 DocumentBuilder 建構函數將單元格插入表中。我們使用 CellFormat.VerticalMerge 屬性對單元格套用垂直合併。我們使用 CellMerge.First 進行第一次儲存格合併，使用 CellMerge.Previous 與前一個儲存格合併，使用 CellMerge.None 進行非垂直合併。

## 第四步：儲存修改後的文檔
最後，我們需要儲存修改後的文件和合併的儲存格。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。

### 使用 Aspose.Words for .NET 進行垂直合併的範例原始程式碼 
```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	//該單元格垂直合併到上面的單元格，並且應該為空。
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 垂直合併 Word 文件中表格中的儲存格。透過遵循此逐步指南並實現提供的 C# 程式碼，您可以輕鬆合併表格中的垂直儲存格。