---
title: 套用輪廓邊框
linktitle: 套用輪廓邊框
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 將輪廓邊框套用到表格的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

在本教學中，我們將引導您逐步完成使用 Aspose.Words for .NET 將輪廓邊框套用到表格的過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將清楚地了解如何使用 Aspose.Words for .NET 操作 Word 文件中的表格邊框。

## 步驟1：定義文檔目錄
首先，您需要設定文檔目錄的路徑。這是您的 Word 文件的儲存位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第2步：上傳文件
接下來，您需要將 Word 文件載入到實例中`Document`班級。

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 第 3 步：訪問表
要套用輪廓邊框，我們需要存取文件中的表格。這`Table`類別代表 Aspose.Words 中的一個表格。

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## 步驟 4：將表格與頁面中心對齊
現在我們可以使用以下命令將表格與頁面中心對齊`Alignment`表的屬性。

```csharp
table. Alignment = Table Alignment. Center;
```

## 步驟 5：擦除現有表格邊框
要開始新的輪廓邊框，我們首先需要從表格中刪除所有現有邊框。這可以使用以下方法完成`ClearBorders()`方法。

```csharp
table. ClearBorders();
```

## 第 6 步：在表格周圍定義綠色邊框
我們現在可以使用以下命令在表格周圍設定綠色邊框`SetBorder()`桌子每一邊的方法。在此範例中，我們使用厚度為 1.5 磅、綠色的「單」型邊框。

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## 步驟7：用背景顏色填滿儲存格
為了改善表格的視覺呈現，我們可以用底色填滿單元格

主意。在此範例中，我們使用淺綠色。

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## 步驟8：儲存修改後的文檔
最後，我們將修改後的文檔儲存到文件中。您可以為輸出文件選擇適當的名稱和位置。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

恭喜！現在，您已使用 Aspose.Words for .NET 將輪廓邊框套用到表格。

### 使用 Aspose.Words for .NET 套用輪廓邊框的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//將表格與頁面中心對齊。
	table.Alignment = TableAlignment.Center;
	//清除表格中任何現有的邊框。
	table.ClearBorders();
	//在桌子周圍設置綠色邊框，但不在桌子內部設置綠色邊框。
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	//用淺綠色純色填滿單元格。
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## 結論
在本教程中，我們學習如何使用 Aspose.Words for .NET 將輪廓邊框套用到表格。遵循此逐步指南，您可以輕鬆地將此功能整合到您的 C# 專案中。操作表格格式是文件處理的一個重要方面，Aspose.Words 提供了強大而靈活的 API 來實現此目的。有了這些知識，您就可以改進 Word 文件的視覺呈現並滿足特定要求。