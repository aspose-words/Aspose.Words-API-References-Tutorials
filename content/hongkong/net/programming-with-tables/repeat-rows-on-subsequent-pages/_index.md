---
title: 在後續頁面重複行
linktitle: 在後續頁面重複行
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件的後續頁面上重複表格行。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 在 Word 文件的後續頁面上重複表格的行。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠指定在 Word 文件中表格的後續頁面上重複的行。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 步驟2：建立文件並初始化文檔產生器
若要使用文件和文件產生器啟動字處理，請依照下列步驟操作：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文件創建
Document doc = new Document();

//初始化文檔產生器
DocumentBuilder builder = new DocumentBuilder(doc);
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 步驟 3：建立包含重複行的表
接下來，我們將建立一個在後續頁面上包含重複行的表格。使用以下程式碼：

```csharp
//表的開頭
builder. StartTable();

//第一行參數的配置（標題行）
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

//插入第一行的第一個儲存格
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

//插入第一行的第二個儲存格
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

//配置以下幾行參數
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

//循環插入以下行中的儲存格
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

//表尾
builder. EndTable();
```

這裡我們使用文件建構器來建立一個包含兩個標題行和多個資料行的表格。這`RowFormat.HeadingFormat`參數用於標記應在後續頁面上重複的標題行。

## 第四步：儲存修改後的文檔
終於美國了

  需要儲存修改後的文檔，並在表格的後續頁面上重複標題行。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。

### 使用 Aspose.Words for .NET 在後續頁面上重複行的範例原始程式碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 在 Word 文件的後續頁面上重複表格的行。透過遵循本逐步指南並實現提供的 C# 程式碼，您可以根據您在 Word 文件中的特定需求指定要重複的行。