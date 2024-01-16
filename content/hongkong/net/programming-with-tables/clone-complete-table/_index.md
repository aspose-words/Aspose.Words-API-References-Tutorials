---
title: 克隆完整表
linktitle: 克隆完整表
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將整個表格複製到 Word 文件中。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/clone-complete-table/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 將整個表格複製到 Word 文件中。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠以程式設計方式將表格複製到 Word 文件中。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 第 2 步：載入文件並存取表
要對錶啟動文字處理，我們需要載入包含該表的文件並存取它。按著這些次序：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入文檔
Document doc = new Document(dataDir + "Tables.docx");

//訪問數組
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 第 3 步：全陣列克隆
接下來，我們將複製整個表格並將其插入文件中原始表格之後。使用以下程式碼：

```csharp
//克隆數組
Table tableClone = (Table)table.Clone(true);

//將複製的表格插入文件中原始表格之後
table.ParentNode.InsertAfter(tableClone, table);

//在兩個表格之間插入一個空段落
//否則它們將在保存時合併為一個（這是由於文件驗證）
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

這裡我們使用的是`Clone`方法建立數組的完整副本。然後我們使用`InsertAfter`將複製的表格插入文件中原始表格之後。我們還在兩個表之間添加一個空段落，以防止它們在保存時被合併。

## 第四步：儲存修改後的文檔
最後，我們需要將修改後的文件與克隆的表一起儲存。使用以下程式碼：

```csharp
//儲存修改後的文檔
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。
  
### 使用 Aspose.Words for .NET 複製完整表格的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//複製表格並將其插入文件中的原始表格之後。
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	//在兩個表格之間插入一個空段落，
	//否則它們將在保存時合併為一個，這與文件驗證有關。
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 將整個表格複製到 Word 文件中。透過遵循本逐步指南並實現提供的 C# 程式碼，您可以透過程式設計方式複製 Word 文件中的表格。此功能可讓您對陣列執行進階操作以滿足您的特定需求。