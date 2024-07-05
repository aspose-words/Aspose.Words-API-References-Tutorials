---
title: 分割表
linktitle: 分割表
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 分割 Word 文件中的表格。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/split-table/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 分割 Word 文件中的表格。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠從 Word 文件中的特定行拆分錶格。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 第 2 步：載入文檔
若要啟動文件的文字處理，請依照下列步驟操作：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入文檔
Document doc = new Document(dataDir + "Tables.docx");
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑，並提供正確的檔案名稱。

## 第三步：劃分錶格
接下來我們將從某一行拆分錶。使用以下程式碼：

```csharp
//檢索第一個表
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

//確定表格的分割線
Row row = firstTable.Rows[2];

//為拆分錶建立一個新容器
Table table = (Table)firstTable.Clone(false);

//將容器插入原始表格之後
firstTable.ParentNode.InsertAfter(table, firstTable);

//新增緩衝段落以保持表格之間的距離
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

//將行從原始表移動到拆分錶
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

這裡我們使用文檔從文檔節點檢索第一個表。然後我們確定要從中拆分資料表的行，在本例中為第三行（索引 2）。然後，我們透過克隆原始表來建立一個新容器，然後將其插入到原始表之後。我們還新增了一個緩衝段落來保持兩個表格之間的距離。然後，我們使用 do-while 循環將行從原始表移至拆分錶，直到到達指定的行。

## 第四步：儲存修改後的文檔
最後，我們需要保存

  使用拆分錶修改的文檔。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。

### 使用 Aspose.Words for .NET 的分割表示例原始碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
//我們將在第三行（含）處拆分錶格。
Row row = firstTable.Rows[2];
//為拆分錶建立一個新容器。
Table table = (Table) firstTable.Clone(false);
//將容器插入原件之後。
firstTable.ParentNode.InsertAfter(table, firstTable);
//新增一個緩衝段落以確保表格保持分開。
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 分割 Word 文件中的表格。透過遵循本逐步指南並實作提供的 C# 程式碼，您可以輕鬆地從 Word 文件中的某一行分割表格。