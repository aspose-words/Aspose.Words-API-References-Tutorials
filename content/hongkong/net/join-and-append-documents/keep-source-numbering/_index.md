---
title: 保留源編號
linktitle: 保留源編號
second_title: Aspose.Words 文件處理 API
description: 了解如何在 Aspose.Words for .NET 中附加文檔，同時保留來源編號格式。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/keep-source-numbering/
---

本教學課程說明如何使用 Aspose.Words for .NET 將來源文檔附加到目標文檔，同時保留編號段落的原始編號格式。

## 第 1 步：設定項目

確保您具備以下先決條件：

- 已安裝 Aspose.Words for .NET 程式庫。您可以從以下位置下載：[Aspose.Releases]https://releases.aspose.com/words/net/ 或使用 NuGet 套件管理器來安裝它。
- 將儲存來源文件和目標文件的文件目錄路徑。

## 步驟 2：建立目標文檔和來源文檔

建立實例`Document`對於目標文檔和來源文檔。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 步驟 3：匯入時保留來源編號

若要保留來源文件中編號段落的編號格式，請建立實例`ImportFormatOptions`並設定`KeepSourceNumbering`到`true`。用一個`NodeImporter`若要將節點從來源文檔匯入到目標文檔，請指定`ImportFormatMode.KeepSourceFormatting`和`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## 第 4 步：匯入並附加段落

迭代來源文件中的段落，並使用以下命令將每個段落匯入到目標文件中`importer`。將導入的節點附加到目標文件的正文。

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## 第五步：儲存修改後的文檔

使用以下命令儲存修改後的文檔`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

這樣就完成了使用 Aspose.Words for .NET 將來源文件附加到目標文件的實現，同時保留原始編號格式。

### 使用 Aspose.Words for .NET 保留來源編號的範例原始碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//匯入編號段落時保持來源清單格式。
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```