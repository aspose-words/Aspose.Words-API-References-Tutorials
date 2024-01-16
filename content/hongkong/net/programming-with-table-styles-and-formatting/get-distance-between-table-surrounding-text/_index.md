---
title: 取得表格周圍文字之間的距離
linktitle: 取得表格周圍文字之間的距離
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 取得 Word 文件中文字和表格之間的距離的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

在本教學中，我們將引導您逐步使用 Aspose.Words for .NET 取得表格中周圍文字之間的距離。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何使用 Aspose.Words for .NET 存取 Word 文件中表格與周圍文字之間的各種距離。

## 步驟1：定義文檔目錄
首先，您需要設定文檔目錄的路徑。這是您的 Word 文件所在的位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：載入現有文檔
接下來，您需要將現有的 Word 文件載入到該實例中`Document`班級。

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 第三步：取得表格與周圍文字之間的距離
要取得表格與周圍文字之間的距離，我們需要使用以下命令存取文件中的表格`GetChild()`方法和`NodeType.Table`財產。然後我們可以使用陣列屬性顯示不同的距離`DistanceTop`, `DistanceBottom`, `DistanceRight`和`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### 使用 Aspose.Words for .NET 取得表格周圍文字之間的距離的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## 結論
在本教程中，我們學習如何使用 Aspose.Words for .NET 來取得表格中周圍文字之間的距離。透過遵循此逐步指南，您可以輕鬆了解 Word 文件中表格與周圍文字之間的各種距離。 Aspose.Words 提供了強大且靈活的 API，用於操作文件中的表格並設定其格式。有了這些知識，您就可以分析與文字相關的表格佈局並滿足特定需求。