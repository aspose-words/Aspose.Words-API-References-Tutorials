---
title: 忽略頁首頁尾
linktitle: 忽略頁首頁尾
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 附加文檔，同時忽略頁首和頁尾內容。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/ignore-header-footer/
---

本教學介紹如何使用 Aspose.Words for .NET 附加文檔，同時忽略頁首和頁尾內容。提供的原始程式碼示範如何設定匯入格式選項以在附加過程中排除頁首和頁尾。

## 第 1 步：設定項目

確保您具備以下先決條件：

- 已安裝 Aspose.Words for .NET 程式庫。您可以從以下位置下載：[Aspose.Releases]https://releases.aspose.com/words/net/ 或使用 NuGet 套件管理器來安裝它。
- 來源文檔和目標文檔所在的文檔目錄路徑。

## 步驟 2：開啟來源文檔和目標文檔

使用以下命令開啟來源文檔和目標文檔`Document`類別構造函數。代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## 第 3 步：設定導入格式選項

建立一個實例`ImportFormatOptions`類別並設定`IgnoreHeaderFooter`財產給`false`。這可確保在附加過程中包含頁首和頁尾內容。

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## 步驟 4：將來源文檔附加到目標文檔

使用`AppendDocument`目標文件附加來源文檔的方法。經過`ImportFormatMode.KeepSourceFormatting`作為第二個參數，導入格式選項作為第三個參數。

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## 步驟 5：儲存目標文檔

最後，使用以下命令儲存修改後的目標文檔`Save`的方法`Document`目的。

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

這樣就完成了使用 Aspose.Words for .NET 附加文件而忽略頁首和頁尾內容的實作。

### 使用 Aspose.Words for .NET 忽略頁首頁腳的範例原始碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```