---
title: 將原始碼放在一起
linktitle: 將原始碼放在一起
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 加入和附加 Word 文檔，同時將來源內容與目標文檔保留在一起。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/keep-source-together/
---

本教學將引導您完成使用 Aspose.Words for .NET 的「保持原始碼在一起」功能的過程。此功能可讓您加入和追加多個 Word 文檔，同時將來源文檔的內容與目標文檔的內容保留在一起。 

## 先決條件

在開始之前，請確保您具備以下條件：

1. Aspose.Words for .NET 已安裝。您可以從 Aspose 網站下載它或透過 NuGet 安裝它。
2. Visual Studio 或任何其他 C# 開發環境。

## 第 1 步：初始化文件目錄

首先，您需要設定文檔目錄的路徑。修改值`dataDir`變數到您的文件所在的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入來源文檔和目標文檔

接下來，您需要使用 Aspose.Words 來載入來源文檔和目標文檔`Document`班級。更新檔名`Document`根據您的文檔名稱建構函數。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 步驟 3：將來源文件設定為顯示在目標文件內容之後

為了確保來源文件緊接在目標文件內容之後出現，您需要設定`SectionStart`來源文檔中第一部分的屬性`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 步驟 4：為來源文件設定「與下一個保持一致」段落格式

若要將來源文件中的段落保留在一起，您可以迭代文件中的每個段落並設定`KeepWithNext`財產給`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## 步驟 5：將來源文檔附加到目標文檔

現在，您可以使用以下命令將來源文檔附加到目標文檔`AppendDocument`的方法`Document`班級。這`ImportFormatMode.KeepSourceFormatting`參數確保在追加操作期間保留來源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第 6 步：儲存最終文檔

最後，使用啟用的「將來源保持在一起」功能儲存合併的文檔`Save`的方法`Document`班級。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### 使用 Aspose.Words for .NET 將原始程式碼保持在一起的範例原始程式碼 

以下是使用 Aspose.Words for .NET 在 C# 中實作「保持原始碼在一起」功能的完整原始碼：


```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//將來源文件設定為直接顯示在目標文件內容之後。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 成功實現了「保持原始碼在一起」功能。最終文檔將包含與來源文檔中的段落合併在一起的合併內容。