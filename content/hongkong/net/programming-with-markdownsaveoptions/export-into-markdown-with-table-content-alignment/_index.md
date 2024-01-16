---
title: 匯出到 Markdown 並對齊表格內容
linktitle: 匯出到 Markdown 並對齊表格內容
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將具有不同對齊方式的表格內容匯出到 Markdown 檔案。
type: docs
weight: 10
url: /zh-hant/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
以下逐步指南解釋了以下 C# 原始程式碼，有助於使用適用於 .NET 的 Aspose.Words 程式庫將內容匯出到具有表格內容對齊的 Markdown 檔案。在使用此程式碼之前，請確保您已在專案中包含 Aspose.Words 程式庫。

## 步驟1：設定文檔目錄路徑

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

請務必指定儲存已編輯文件的文件目錄的正確路徑。

## 第 2 步：建立文件和文件產生器

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

這裡我們創建一個實例`Document`類別和一個實例`DocumentBuilder`類，它允許我們操作文件並添加元素。

## 步驟 3：在表格中插入具有不同段落對齊方式的儲存格

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

我們使用文件產生器將儲存格插入表格中，並為每個儲存格設定不同的段落對齊方式。

## 步驟 4：設定 Markdown 匯出選項並儲存修改後的文檔

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

我們使用不同的表格內容對齊方式設定 Markdown 匯出選項，然後使用每個對齊選項儲存修改後的文件。

### 使用 Aspose.Words for .NET 匯出到 Markdown 並使用表格內容對齊的範例原始程式碼

```csharp

            
	//文檔目錄的路徑。
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	//使表格內的所有段落對齊。
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	//在這種情況下，對齊方式將從對應表列的第一段中取得。
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	//儲存修改後的文檔
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
