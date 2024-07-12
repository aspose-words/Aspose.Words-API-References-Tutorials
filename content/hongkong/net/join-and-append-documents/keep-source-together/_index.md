---
title: 將原始碼放在一起
linktitle: 將原始碼放在一起
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 合併 Word 文檔，同時保留格式。這份綜合指南涵蓋了從設定到執行的所有內容。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/keep-source-together/
---
## 介紹

在當今的數位時代，以程式設計方式操作 Word 文件對於各個行業都至關重要。 Aspose.Words for .NET 讓開發人員能夠有效率地自動化文件處理任務。本綜合指南將引導您完成使用 Aspose.Words for .NET 合併文件同時保留來源格式的程序。

## 先決條件

在深入研究使用 Aspose.Words for .NET 進行文件合併之前，請確保您具備以下條件：

- Visual Studio：用於 .NET 開發的整合開發環境 (IDE)。
- Aspose.Words for .NET：在您的開發環境中安裝和設定。
- 熟悉 C#：對 C# 程式語言有基本了解。

## 導入命名空間

首先，導入必要的命名空間：

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## 第 1 步：載入文檔

首先，將來源文檔和目標文檔載入Aspose.Words中`Document`對象。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR_DOCUMENT_DIRECTORY/";

//載入來源文檔和目標文檔
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 第 2 步：設定部分開始

配置部分開始以確保來源文檔內容在目標文件之後持續流動。

```csharp
//將來源文件設定為直接顯示在目標文件內容之後
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 第三步：將段落放在一起

為了保持格式完整性，請標記來源文件中的每個段落以與下一個段落保持一致。

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## 第 4 步：附加文件

使用合併文檔`AppendDocument`方法，確保保留來源文件的格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步驟 5：儲存合併文檔

最後，將合併後的文件儲存到所需位置。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

## 結論

總之，Aspose.Words for .NET 簡化了合併 Word 文件的任務，同時無縫保留原始格式。此功能對於需要自動文件處理的應用程式至關重要。

## 常見問題解答

### Aspose.Words for .NET 可以合併不同格式的文件嗎？
是的，它可以合併文檔，無論其格式如何，並保持來源格式。

### Aspose.Words for .NET 支援高效合併大型文件嗎？
當然，它可以以最佳性能處理大型文件。

### Aspose.Words for .NET 有試用版嗎？
是的，您可以下載免費試用版[這裡](https://releases.aspose.com/).

### 如何獲得 Aspose.Words for .NET 的技術支援？
技術支援可透過[Aspose.Words 論壇](https://forum.aspose.com/c/words/8).

### 我可以購買 Aspose.Words for .NET 的臨時授權嗎？
是的，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).