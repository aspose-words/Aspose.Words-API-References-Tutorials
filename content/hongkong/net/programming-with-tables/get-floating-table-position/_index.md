---
title: 取得浮動表位置
linktitle: 取得浮動表位置
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 取得 Word 文件中浮動表格的位置。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/get-floating-table-position/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 取得 Word 文件中浮動表格的位置。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠以程式設計方式取得 Word 文件中浮動表格的定位屬性。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 第 2 步：載入文件並存取表格
要開始使用表格進行文字處理，我們需要載入包含它們的文件並存取它們。按著這些次序：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入文檔
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。另外，請確保文件包含浮動表格。

## 步驟3：取得浮動表定位屬性
接下來，我們將循環遍歷文件中的所有表格並取得浮動表格定位屬性。使用以下程式碼：

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
//如果陣列是浮點類型，則列印其定位屬性。
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

這裡我們使用的是`foreach`循環遍歷文件中的所有數組。我們透過檢查數組是否為 float 類型來檢查`TextWrapping`財產。如果是這樣，我們列印表格的定位屬性，例如水平錨點、垂直錨點、絕對水平和垂直距離、重疊權限、絕對水平距離和相對垂直對齊。
 
### 使用 Aspose.Words for .NET 取得浮動表格位置的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		//如果表格是浮動類型，則列印其定位屬性。
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 取得 Word 文件中浮動表格的位置。透過遵循本逐步指南並實現提供的 C# 程式碼，您可以透過程式設計方式取得 Word 文件中浮動表格的定位屬性。此功能可讓您根據您的特定需求分析和操作浮動表。