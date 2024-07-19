---
title: 行格式停用跨頁中斷
linktitle: 行格式停用跨頁中斷
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中停用跨多個頁面的表格換行符。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/row-format-disable-break-across-pages/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 停用 Word 文件中多頁表格的換行符號。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠停用 Word 文件表格中所有行的換行。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 第 2 步：載入文檔
若要啟動文件的文字處理，請依照下列步驟操作：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入文檔
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑，並提供正確的檔案名稱。

## 步驟 3：停用表格換行符
接下來，我們將停用表中所有行的行中斷。使用以下程式碼：

```csharp
//檢索表
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

//停用表中所有行的換行符
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

在這裡，我們使用文件來取得第一個表，然後使用 foreach 迴圈迭代表中的所有行。在循環內部，我們透過設定來停用每行的行中斷`RowFormat.AllowBreakAcrossPages`財產給`false`.

## 第四步：儲存修改後的文檔
最後，我們需要在停用表格換行符的情況下儲存修改後的文件。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。

### 使用 Aspose.Words for .NET 行格式停用跨頁分隔的範例原始碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
//停用表中所有行的跨頁分隔。
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 停用 Word 文件中多頁表格的換行符號。透過遵循此逐步指南並實施提供的 C# 程式碼，您可以將此停用應用到 Word 文件中的表格。