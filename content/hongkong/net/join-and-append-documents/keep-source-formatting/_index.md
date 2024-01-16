---
title: 保持來源格式
linktitle: 保持來源格式
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將來源文檔附加到目標文檔，同時保留原始格式。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/keep-source-formatting/
---

本教學課程示範如何使用 Aspose.Words for .NET 將來源文檔附加到目標文檔，同時保留來源文檔的原始格式。

## 第 1 步：設定項目

確保您具備以下先決條件：

- 已安裝 Aspose.Words for .NET 程式庫。您可以從以下位置下載：[Aspose.Releases]https://releases.aspose.com/words/net/ 或使用 NuGet 套件管理器來安裝它。
- 將儲存來源文件和目標文件的文件目錄路徑。

## 步驟 2：建立目標文檔和來源文檔

建立實例`Document`對於目標文檔和來源文檔。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## 步驟 3：將來源文檔附加到目標文檔

使用`AppendDocument`目標文件附加來源文檔的方法。經過`ImportFormatMode.KeepSourceFormatting`作為匯入格式模式，保留來源文件的原始格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第四步：儲存修改後的文檔

使用以下命令儲存修改後的文檔`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

這樣就完成了使用 Aspose.Words for .NET 將來源文檔附加到目標文檔，同時保留原始格式的實作。

### 使用 Aspose.Words for .NET 保持來源格式的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	//將來源文檔附加到目標文檔。
	//透過格式模式以在匯入時保留來源文件的原始格式。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```