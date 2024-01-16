---
title: 忽略文字框
linktitle: 忽略文字框
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 附加文檔，同時忽略文字方塊格式。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/ignore-text-boxes/
---

本教學課程介紹如何使用 Aspose.Words for .NET 附加文檔，同時保留文字方塊的格式。提供的原始程式碼示範如何設定導入格式選項以在附加過程中包含文字方塊。

## 第 1 步：設定項目

確保您具備以下先決條件：

- 已安裝 Aspose.Words for .NET 程式庫。您可以從以下位置下載：[Aspose.Releases]https://releases.aspose.com/words/net/ 或使用 NuGet 套件管理器來安裝它。
- 來源文檔和目標文檔所在的文檔目錄路徑。

## 步驟 2：開啟來源文檔和目標文檔

使用以下命令開啟來源文檔和目標文檔`Document`類別構造函數。代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 第 3 步：設定導入格式選項

建立一個實例`ImportFormatOptions`類別並設定`IgnoreTextBoxes`財產給`false`。這可確保在附加過程中包含文字框，同時保留其格式。

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## 第 4 步：附加文字方塊內容

創建一個`NodeImporter`物件並使用它將文字方塊節點從來源文件匯入到目標文件。迭代來源文件中的每個段落並將其匯入到目標文件。

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## 步驟 5：儲存目標文檔

最後，使用以下命令儲存修改後的目標文檔`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

這樣就完成了使用 Aspose.Words for .NET 附加文件同時保留文字方塊格式的實作。

### 使用 Aspose.Words for .NET 忽略文字方塊的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//導入時保持來源文字方塊的格式。
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```