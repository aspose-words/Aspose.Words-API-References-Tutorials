---
title: 修改行格式
linktitle: 修改行格式
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 變更表格行格式的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

在本教學中，我們將引導您完成使用 Aspose.Words for .NET 變更表格行格式的逐步流程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何使用 Aspose.Words for .NET 變更 Word 文件中表格行的邊框、高度和換行符。

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

## 第三步：訪問要修改的行
要更改表格行的格式，我們需要導航到表中的特定行。我們使用`GetChild()`和`FirstRow`方法來取得對錶第一行的參考。

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## 步驟 4：更改行格式
現在我們可以使用屬性來更改行格式`RowFormat`班級。例如，我們可以刪除線邊框、設定自動高度並允許換行。

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### 使用 Aspose.Words for .NET 修改行格式的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//檢索表格中的第一行。
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 變更表格行的格式。透過遵循此逐步指南，您可以輕鬆調整 Word 文件中表格的邊框、高度和行換行符。 Aspose.Words 提供了強大且靈活的 API，用於操作文件中的表格並設定其格式。有了這些知識，您就可以根據您的特定需求自訂表格的視覺佈局。