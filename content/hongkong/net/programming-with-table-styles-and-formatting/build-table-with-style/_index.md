---
title: 建立具有風格的表格
linktitle: 建立具有風格的表格
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 建立具有自訂樣式的表格的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

在本教學中，我們將引導您逐步完成使用 Aspose.Words for .NET 建立樣式表的過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何使用 Aspose.Words for .NET 在 Word 文件中建立具有自訂樣式的表格。

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

## 步驟 3：開始一個新表格並插入一個儲存格
要開始建立表，我們使用`StartTable()`文檔生成器的方法，然後我們使用`InsertCell()`方法。

```csharp
Table table = builder. StartTable();
builder.InsertCell();
```

## 第四步：定義表格的樣式
現在我們可以使用以下命令來設定表格樣式`StyleIdentifier`財產。在此範例中，我們使用「MediumShading1Accent1」樣式。

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## 步驟 5：將樣式選項套用到表格
我們可以使用以下命令指定樣式應格式化哪些特徵`StyleOptions`數組的屬性。在此範例中，我們套用以下選項：「FirstColumn」、「RowBands」和「FirstRow」。

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## 第6步：自動調整表格大小
為了根據數組的內容自動調整數組的大小，我們使用`AutoFit()`方法與`AutoFitBehavior.AutoFitToContents`行為。

```csharp
table.AutoFit(AutoFitBehavior.AutoFitToContents);
```

## 步驟 7：為儲存格新增內容
現在我們可以使用以下命令為儲存格新增內容`Writeln()`和`InsertCell()`文檔生成器的方法。在此範例中，我們新增「Item」和「Quantity」的標題（

kg）”和相應的數據。

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder.InsertCell();
builder.Writen("Quantity (kg)");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Apples");
builder.InsertCell();
builder.Writeln("20");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Bananas");
builder.InsertCell();
builder.Writen("40");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Carrots");
builder.InsertCell();
builder.Writeln("50");
builder.EndRow();
```

## 步驟8：儲存修改後的文檔
最後，我們將修改後的文檔儲存到文件中。您可以為輸出文件選擇適當的名稱和位置。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

恭喜！現在您已經使用 Aspose.Words for .NET 建立了一個自訂樣式的表格。

### 使用 Aspose.Words for .NET 建立帶有樣式的表格的範例原始程式碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();
//在設定任何表格格式之前，我們必須先插入至少一行。
builder.InsertCell();
//根據唯一樣式識別碼設定使用的表格樣式。
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
//應用程式應按樣式格式化哪些功能。
table.StyleOptions =
	TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
table.AutoFit(AutoFitBehavior.AutoFitToContents);
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder.InsertCell();
builder.Writeln("Quantity (kg)");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Apples");
builder.InsertCell();
builder.Writeln("20");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Bananas");
builder.InsertCell();
builder.Writeln("40");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Carrots");
builder.InsertCell();
builder.Writeln("50");
builder.EndRow();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 建立樣式表。透過遵循此逐步指南，您可以輕鬆自訂 Word 文件中的表格樣式。 Aspose.Words 提供了強大且靈活的 API，用於操作文件中的表格並設定其格式。有了這些知識，您就可以改進 Word 文件的視覺呈現並滿足特定需求。