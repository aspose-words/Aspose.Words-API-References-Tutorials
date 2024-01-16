---
title: 合併行
linktitle: 合併行
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 組合 Word 文件中的表格行。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/combine-rows/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 組合 Word 文件中的表格行。我們將按照逐步指南來理解程式碼並實現此功能。在本教學課程結束時，您將能夠以程式設計方式操作和合併 Word 文件中的表格行。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 第 2 步：載入文件並存取表格
要開始使用表格進行文字處理，我們需要載入包含它們的文件並存取它們。按著這些次序：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入文檔
Document doc = new Document(dataDir + "Tables.docx");

//訪問表
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 步驟 3：合併表格行
接下來，我們將第二個表格的行合併到第一個表格的結尾。使用以下程式碼：

```csharp
//表格行的組合
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

這裡我們使用一個`while`循環迭代第二個數組的所有行，並使用以下命令將它們添加到第一個數組的末尾`Add`方法。接下來，我們使用以下命令從文件中刪除第二個表`Remove`方法。

## 第四步：儲存修改後的文檔
最後，我們需要將修改後的文檔與組合的表格行一起儲存。使用以下程式碼：

```csharp
//儲存修改後的文檔
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。

### 使用 Aspose.Words for .NET 合併行的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	//第二個表中的行將附加到第一個表的末尾。
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	//將目前表中的所有行追加到下一個表中
	//具有不同儲存格數量和寬度的儲存格可以合併到一張表中。
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 組合 Word 文件中的表格行。透過遵循本逐步指南並實現提供的 C# 程式碼，您可以透過程式設計 Word 文件中的表格行。此功能可讓您有效地將資料合併並組織到表中。