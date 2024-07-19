---
title: 設定具有不同邊框的表格和儲存格格式
linktitle: 設定具有不同邊框的表格和儲存格格式
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 設定具有不同邊框的表格和儲存格格式的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

在本教學中，我們將引導您逐步使用 Aspose.Words for .NET 設定具有不同邊框的表格和儲存格格式。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何使用 Aspose.Words for .NET 將自訂邊框套用到 Word 文件中的特定表格和儲存格。

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

## 第 3 步：建立一個新表格並新增儲存格
要開始建立表，我們使用`StartTable()`文檔生成器的方法，然後我們使用`InsertCell()`方法，我們將單元格的內容寫入使用`Writeln()`方法。

```csharp
Table table = builder. StartTable();
builder.InsertCell();
//設定整個表格的邊框。
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
//設定該單元格的填滿。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
//為第二個儲存格指定不同的儲存格填入。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
//清除之前操作的儲存格格式。
builder.CellFormat.ClearFormatting();
builder.InsertCell();
//為該行中的第一個儲存格建立較粗的邊框。將會有所不同
//相對於為表定義的邊框。
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## 步驟 4：儲存文檔

  修正的
最後將修改後的文檔儲存到文件中。您可以為輸出文件選擇適當的名稱和位置。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

恭喜！現在您已經使用 Aspose.Words for .NET 設定了具有不同邊框的表格和儲存格的格式。

### 使用 Aspose.Words for .NET 設定具有不同邊框的表格和儲存格格式的範例原始程式碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();
builder.InsertCell();
//設定整個表格的邊框。
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
//設定該單元格的單元格底紋。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
//為第二個單元格指定不同的單元格底紋。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
//清除之前操作中的儲存格格式。
builder.CellFormat.ClearFormatting();
builder.InsertCell();
//為該行的第一個儲存格建立更大的邊框。這將會有所不同
//與為表格設定的邊框相比。
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 設定具有不同邊框的表格和儲存格的格式。透過遵循此逐步指南，您可以輕鬆自訂 Word 文件中的表格和儲存格邊框。 Aspose.Words 提供了強大且靈活的 API，用於操作文件中的表格並設定其格式。有了這些知識，您就可以改進 Word 文件的視覺呈現並滿足特定需求。