---
title: 自動適應頁面寬度
linktitle: 自動適應頁面寬度
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 自動調整 Word 文件中表格的頁面寬度。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/auto-fit-to-page-width/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 自動調整表格以適應 Word 文件中的頁面寬度。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠以程式設計方式操作 Word 文件中的表格。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 第 2 步：建立和設定文檔
要使用表格啟動文字處理，我們需要建立一個文件並配置文件產生器。按著這些次序：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//建立文件和文件產生器
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 第 3 步：插入並配置表
接下來，我們將在文件中插入一個表格，其寬度佔頁面寬度的一半。使用以下程式碼：

```csharp
//插入表格並配置其寬度
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

這裡我們使用文件產生器開始建立表格，插入儲存格，並將表格的首選寬度設定為頁面寬度的 50%。然後我們在每個單元格中添加文字。

## 第四步：儲存修改後的文檔
最後，我們需要儲存修改後的文檔，並將表格調整為頁面寬度。使用以下程式碼：

```csharp
//儲存修改後的文檔
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。
  
### 使用 Aspose.Words for .NET 自動適應頁面寬度的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//插入寬度佔頁面寬度一半的表格。
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 將表格自動調整為 Word 文件中的頁面寬度。透過遵循本逐步指南並實現提供的 C# 程式碼，您可以以程式設計方式操作 Word 文件中的表格。此功能可讓您根據頁面動態調整表格的寬度，從而提供專業且具有視覺吸引力的文件。