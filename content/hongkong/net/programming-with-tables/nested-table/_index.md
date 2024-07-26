---
title: 巢狀表
linktitle: 巢狀表
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中建立巢狀表格。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/nested-table/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 在 Word 文件中建立巢狀表格。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠以程式設計方式在 Word 文件中建立巢狀表格。

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

## 第 3 步：建立巢狀表
接下來，我們將透過將單元格插入外部表並在第一個單元格內建立新表來建立巢狀表。使用以下程式碼：

```csharp
//插入外表的第一個單元格
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

//插入外表的第二個單元格
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

//外部表的終止
builder. EndTable();

//移至外表的第一個單元格
builder.MoveTo(cell.FirstParagraph);

//建構內表
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

//內表結束
builder. EndTable();
```

這裡我們使用文檔產生器將儲存格和內容插入到外表中。然後，我們將文件建構器遊標移至外部表格的第一個儲存格，並透過插入儲存格和內容在內部建立一個新表格。

## 第四步：儲存修改後的文檔
最後，我們需要使用巢狀表來儲存修改後的文件。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。

### 使用 Aspose.Words for .NET 的巢狀表格的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	//此呼叫對於在第一個表中建立巢狀表非常重要。
	//如果沒有此調用，下面插入的單元格將被附加到外表。
	builder.EndTable();
	//移至外表的第一個儲存格。
	builder.MoveTo(cell.FirstParagraph);
	//建構內表。
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 在 Word 文件中建立巢狀表格。透過遵循本逐步指南並實現提供的 C# 程式碼，您可以根據您的特定需求以程式設計方式在 Word 文件中建立巢狀表格。
