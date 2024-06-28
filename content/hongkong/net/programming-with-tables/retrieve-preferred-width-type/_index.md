---
title: 擷取首選寬度類型
linktitle: 擷取首選寬度類型
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 擷取 Word 表格中儲存格的類型和首選寬度值。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/retrieve-preferred-width-type/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 從 Word 文件的表格儲存格中擷取首選寬度類型及其值。我們將按照逐步指南來理解程式碼並實現此功能。在本教學課程結束時，您將能夠擷取 Word 文件表格中特定儲存格的首選寬度類型（絕對、相對或自動）及其值。

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

## 步驟 3：擷取首選寬度類型和值
接下來，我們將擷取特定表格單元格的首選寬度類型及其值。使用以下程式碼：

```csharp
//檢索表
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

//啟動自動工作台調整
table. AllowAutoFit = true;

//檢索第一行的第一個單元格
Cell firstCell = table.FirstRow.FirstCell;

//擷取首選寬度類型及其值
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

這裡我們使用文件來取得第一個表格，然後我們啟用自動表格匹配`AllowAutoFit`財產。然後我們檢索表格第一行的第一個儲存格。從此單元格中，我們可以使用以下命令檢索首選寬度類型`PreferredWidth.Type`財產及其價值`PreferredWidth.Value`財產。

### 使用 Aspose.Words for .NET 擷取首選寬度類型的範例原始程式碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 從 Word 文件的表格儲存格中擷取首選寬度類型及其值。透過遵循此逐步指南並實施提供的 C# 程式碼，您可以擷取 Word 文件表格中特定儲存格的此資訊。