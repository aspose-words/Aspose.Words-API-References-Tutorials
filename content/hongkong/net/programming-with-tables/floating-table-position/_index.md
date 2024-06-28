---
title: 浮動工作台位置
linktitle: 浮動工作台位置
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將表格放置在 Word 文件中的浮動位置。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/floating-table-position/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 將表格放置在 Word 文件中的浮動位置。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠以程式方式控制 Word 文件中浮動表格的位置和對齊方式。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 第 2 步：載入文件並存取表格
要對錶啟動文字處理，我們需要載入包含該表的文件並存取它。按著這些次序：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入文檔
Document doc = new Document(dataDir + "Table wrapped by text.docx");

//訪問數組
Table table = doc.FirstSection.Body.Tables[0];
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。另外，請確保文件包含將位於浮動位置的表格。

## 第三步：定位浮板
接下來，我們將使用 Aspose.Words for .NET 提供的屬性將表格定位在浮動位置。使用以下程式碼：

```csharp
//定位浮動台
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

這裡我們使用`AbsoluteHorizontalDistance`屬性設定表格距頁面左邊緣的絕對水平距離。我們也使用`RelativeVerticalAlignment`屬性來設定表格與周圍內容的相對垂直對齊方式。

## 第四步：儲存修改後的文檔
最後，我們需要儲存修改後的文檔，並將表格放置在浮動位置。使用以下程式碼：

```csharp
//儲存修改後的文檔
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。

### 使用 Aspose.Words for .NET 浮動表格位置的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 將表格放置在 Word 文件中的浮動位置。透過遵循本逐步指南並實現提供的 C# 程式碼，您可以透過程式設計方式控制 Word 文件中浮動表格的位置和對齊方式。