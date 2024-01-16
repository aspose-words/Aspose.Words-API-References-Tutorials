---
title: 從 Html 插入表格
linktitle: 從 Html 插入表格
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將 HTML 表格插入 Word 文件中。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/insert-table-from-html/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 將表格從 HTML 插入到 Word 文件中。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠以程式設計方式將 HTML 中的表格插入到 Word 文件中。

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

## 步驟 3：從 HTML 插入表格
接下來，我們將使用 HTML 程式碼將表格插入文件中。使用以下程式碼：

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

這裡我們使用`InsertHtml`文件產生器的方法來插入包含表格的 HTML。指定的 HTML 建立一個包含兩行和每行兩個單元格的表格。您可以根據需要透過修改 HTML 程式碼來自訂表格的內容。

## 第四步：儲存修改後的文檔
最後，我們需要保存修改後的文件以及從 HTML 插入的表格。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。

### 使用 Aspose.Words for .NET 從 Html 插入表格的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//請注意，AutoFitSettings 不適用於從 HTML 插入的表格。
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 將表格從 HTML 插入到 Word 文件中。透過遵循本逐步指南並實現提供的 C# 程式碼，您可以以程式設計方式將 HTML 中的表格插入到 Word 文件中。此功能可讓您將 HTML 來源中的表格資料轉換並匯入到 Word 文件中。
