---
title: 不同的頁面設定
linktitle: 不同的頁面設定
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 附加具有不同頁面設定設定的文件。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/different-page-setup/
---

本教學課程介紹如何使用 Aspose.Words for .NET 將具有不同頁面設定設定的文件附加到另一個文件。提供的原始程式碼示範如何為來源文件和目標文件設定不同的頁面設定並確保正確的連續性和編號。

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

## 步驟 3：設定來源文檔的頁面設置

調整來源文件的頁面設定以確保正確的連續性和編號。在此範例中，我們將部分開始設定為`SectionStart.Continuous`並重新開始頁碼編號。我們還確保頁面寬度、高度和方向與目標文件的最後一部分相符。

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## 步驟 4：修改段落格式

若要保持正確的格式，請遍歷來源文件中的所有段落並設定`KeepWithNext`財產給`true`。這可確保段落在附加過程中保持在一起。

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## 步驟 5：將來源文檔附加到目標文檔

使用`AppendDocument`目標文檔的方法，將修改後的來源文檔附加到目標文檔，並保留來源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步驟 6：儲存目標文檔

最後，使用以下命令儲存修改後的目標文檔`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

這樣就完成了使用 Aspose.Words for .NET 附加具有不同頁面設定設定的文件的實作。

### 使用 Aspose.Words for .NET 進行不同頁面設定的範例原始碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//將來源文件設定為在目標文件結尾後直接繼續。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	//在來源文檔的開頭重新開始頁碼編號。
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	//為確保當來源文件具有不同的頁面設定設定時不會發生這種情況，請確保
	//目標文件最後一部分的設定是相同的。
	//如果來源文件中還有後續的連續部分，
	//需要對這些部分重複此操作。
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	//迭代來源文檔中的所有部分。
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```