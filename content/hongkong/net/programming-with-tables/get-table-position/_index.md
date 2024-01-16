---
title: 取得桌子位置
linktitle: 取得桌子位置
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 取得 Word 文件中表格的位置。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/get-table-position/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 取得 Word 文件中表格的位置。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠以程式設計方式取得 Word 文件中的表格定位屬性。

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

請務必將「您的文件目錄」替換為文件目錄的實際路徑。另外，請確保文件包含您想要取得其位置的表格。

## 第 3 步：取得數組定位屬性
接下來，我們將檢查陣列的定位類型並取得適當的定位屬性。使用以下程式碼：

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

這裡我們使用一個條件來檢查陣列是否為 float 類型。如果是這樣，我們列印`RelativeHorizontalAlignment`和`RelativeVerticalAlignment`屬性來取得表格的相對水平和垂直對齊方式。否則，我們會列印`Alignment`屬性來取得數組對齊方式。

### 使用 Aspose.Words for .NET 取得表格位置的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 取得 Word 文件中表格的位置。透過遵循本逐步指南並實現提供的 C# 程式碼，您可以透過程式設計方式取得 Word 文件中的表格定位屬性。此功能可讓您根據陣列的特定位置來分析和操作陣列。