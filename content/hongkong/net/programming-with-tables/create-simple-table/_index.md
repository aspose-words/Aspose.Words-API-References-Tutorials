---
title: 建立簡單表
linktitle: 建立簡單表
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中建立簡單的表格。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/create-simple-table/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 在 Word 文件中建立簡單的表格。我們將按照逐步指南來理解程式碼並實現此功能。在本教學課程結束時，您將能夠以程式設計方式在 Word 文件中建立自訂表格。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 步驟2：建立文件並初始化文檔產生器
要開始建置表，我們需要建立一個新文件並初始化文件建構器。按著這些次序：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//建立文檔並初始化文檔產生器
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 第 3 步：建構陣列
接下來，我們將使用文件建構器提供的方法來建立表格。使用以下程式碼：

```csharp
//開始數組構建
builder. StartTable();

//建構第一行第一個單元格
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

//第一行第二個單元格的構造
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//呼叫以下方法結束第一行並開始新行
builder. EndRow();

//第二行第一個單元格的構造
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

//第二排第二個單元的構造
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

//呼叫next方法結束第二行
builder. EndRow();

//表明表的建構完成
builder. EndTable();
```

這裡我們使用文件建構器來一步一步建立表格。我們首先調用`StartTable()`初始化表，然後使用`InsertCell()`插入細胞和`Write()`在每個儲存格中新增內容。我們也使用`EndRow()`結束一行並開始新行。最後，我們調用`EndTable()`表明表建構完成。

## 步驟 4：儲存文檔
最後，我們需要保存

  包含已建立的表格的文件。使用以下程式碼：

```csharp
//儲存文件
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。

### 使用 Aspose.Words for .NET 建立簡單表格的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//開始建表。
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	//建構第二個單元格。
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	//呼叫以下方法結束該行並開始新行。
	builder.EndRow();
	//建立第二行的第一個單元格。
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	//建構第二個單元格。
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//表明我們已經完成了表格的建構。
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 在 Word 文件中建立簡單的表格。透過遵循本逐步指南並實施提供的 C# 程式碼，您可以以程式設計方式在 Word 文件中建立自訂表格。此功能可讓您以結構化且清晰的方式格式化和組織資料。