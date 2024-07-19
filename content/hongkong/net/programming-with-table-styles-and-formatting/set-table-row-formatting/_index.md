---
title: 設定表格行格式
linktitle: 設定表格行格式
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 設定表格行格式的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

在本教學中，我們將引導您完成使用 Aspose.Words for .NET 設定表格行格式的逐步流程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何使用 Aspose.Words for .NET 調整 Word 文件中表格行的高度和填充。

## 步驟1：定義文檔目錄
首先，您需要設定文檔目錄的路徑。這是您要儲存編輯的 Word 文件的位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟 2：建立新文檔和文檔產生器
接下來，您需要建立一個新的實例`Document`類別和該文檔的文檔建構子。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：建立一個新表格並新增一個儲存格
要開始建立表，我們使用`StartTable()`文檔建構函數的方法，然後我們使用`InsertCell()`方法。

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## 步驟 4：定義行格式
現在我們可以透過訪問來設定行格式`RowFormat`的對象`DocumentBuilder`目的。我們可以使用對應的屬性來設定行高和邊距（paddings）。

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## 第 5 步：設定表格邊距
接下來，我們可以透過存取對應的屬性來設定表格填充`Table`目的。這些邊距將會套用至表格的所有行。

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## 第 6 步：為行新增內容
最後，我們可以使用文檔產生器將內容新增到該行`Writeln()`方法。

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## 步驟 7：完成表格並儲存文檔
在

最後，我們使用以下命令完成表格的創建`EndRow()`和`EndTable()`方法，然後我們將修改後的文件儲存到文件中。

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### 使用 Aspose.Words for .NET 設定表格行格式的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	//這些格式屬性在表上設定並套用至表中的所有行。
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 設定表格行格式。遵循此逐步指南，您可以輕鬆調整 Word 文件中的表格行高和邊距。 Aspose.Words 提供了強大且靈活的 API，用於操作文件中的表格並設定其格式。有了這些知識，您就可以根據您的特定需求自訂表格的視覺佈局。