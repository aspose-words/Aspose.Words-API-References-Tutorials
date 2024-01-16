---
title: 展開儲存格的格式並從樣式行
linktitle: 展開儲存格的格式並從樣式行
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 將表格樣式的格式擴展到儲存格和行的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

在本教學中，我們將引導您逐步完成使用 Aspose.Words for .NET 將格式從樣式擴展到儲存格和行的過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何使用 Aspose.Words for .NET 將表格樣式格式套用至 Word 文件中的特定儲存格和行。


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

## 步驟 3：轉到第一個表格的第一個儲存格
首先，我們需要導航到文件中第一個表格的第一個儲存格。我們使用`GetChild()`和`FirstRow.FirstCell`方法來取得第一個儲存格的參考。

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## 步驟 4：顯示初始儲存格格式
在擴展表格的樣式之前，我們顯示儲存格目前的背景顏色。該值應該為空，因為目前格式儲存在表格的樣式中。

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## 步驟 5：將表格樣式擴充為直接格式化
現在我們將表格樣式擴展為使用文件的直接格式`ExpandTableStylesToDirectFormatting()`方法。

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## 步驟 6：顯示樣式擴充後的儲存格格式
現在我們在展開表格樣式後顯示儲存格的背景顏色。應從表格樣式套用藍色背景顏色。

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### 使用 Aspose.Words for .NET 擴充單元格格式和從樣式行的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	//取得文件中第一個表格的第一個儲存格。
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	//首先列印單元格底紋的顏色。
	//該值應該為空，因為目前著色儲存在表格樣式中。
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	//現在，在展開表格樣式後列印儲存格底紋。
	//應從表格樣式套用藍色背景圖案顏色。
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 將表格樣式的格式擴展到儲存格和行。透過遵循此逐步指南，您可以輕鬆地將表格樣式格式套用至 Word 文件中的特定儲存格和行。 Aspose.Words 提供了強大且靈活的 API，用於操作文件中的表格並設定其格式。有了這些知識，您就可以進一步自訂 Word 文件的佈局和簡報。