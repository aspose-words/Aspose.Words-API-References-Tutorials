---
title: 應用程式格式
linktitle: 應用程式格式
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 將行格式套用至表格的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

在本教學中，我們將引導您逐步完成使用 Aspose.Words for .NET 將行格式套用至表格的過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將清楚地了解如何使用 Aspose.Words for .NET 格式化 Word 文件中的表格行。

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

## 第 3 步：啟動新板
要套用行格式，我們必須先使用`StartTable()`文檔建構函數的方法。

```csharp
Table table = builder. StartTable();
```

## 步驟 4：插入儲存格並轉到行格式
現在我們可以將一個單元格插入表中，並使用文件生成器存取該單元格的行格式`InsertCell()`和`RowFormat`方法。

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## 第5步：設定行高
為了設定行高，我們使用`Height`和`HeightRule`行格式的屬性。在此範例中，我們將行高設為 100 點並使用`Exactly`規則。

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## 步驟 6：定義表格格式
某些格式化屬性可以在表格本身上設置，並套用於所有表格行。在此範例中，我們使用以下命令設定表格邊距屬性`LeftPadding`, `RightPadding`, `TopPadding`和`BottomPadding`特性。

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## 第 7 步：向行新增內容
現在我們可以

我們將使用文檔建構函數的方法向該行添加內容。在這個例子中，我們使用`Writeln()`方法將文字加入行中。

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## 步驟8：完成線條和表格
將內容新增至行後，我們可以使用以下命令結束該行`EndRow()`方法，然後使用結束表`EndTable()`方法。

```csharp
builder. EndRow();
builder. EndTable();
```

## 步驟9：儲存修改後的文檔
最後，我們將修改後的文檔儲存到文件中。您可以為輸出文件選擇適當的名稱和位置。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

恭喜！現在，您已使用 Aspose.Words for .NET 將行格式套用至表格。

### 使用 Aspose.Words for .NET 應用程式格式的範例原始程式碼 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 將行格式套用至表格。遵循此逐步指南，您可以輕鬆地將此功能整合到您的 C# 專案中。操作表格行格式是文件處理的一個重要方面，Aspose.Words 提供了強大而靈活的 API 來實現此目的。有了這些知識，您就可以改進 Word 文件的視覺呈現並滿足特定要求。