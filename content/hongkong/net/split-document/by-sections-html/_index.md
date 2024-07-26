---
title: 按 HTML 部分拆分 Word 文件
linktitle: 按章節 Html
second_title: Aspose.Words 文件處理 API
description: 透過完整的程式碼範例，了解如何使用 Aspose.Words for .NET 將 Word 文件按部分 Html 分割。
type: docs
weight: 10
url: /zh-hant/net/split-document/by-sections-html/
---

在此範例中，我們將向您展示如何使用 Aspose.Words for .NET 的按 HTML 部分功能將 Word 文件分割為 HTML 格式的單獨部分。請按照以下步驟了解原始程式碼並為每個部分產生單獨的 HTML 文件。

## 第 1 步：載入文檔

首先，指定文檔的目錄並將文檔載入到 Document 物件中。就是這樣：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## 步驟 2：將文件分割為 HTML 格式的部分

現在我們將設定儲存選項以將文件劃分為 HTML 格式的部分。操作方法如下：

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### 使用 Aspose.Words for .NET 的按部分 HTML 的範例原始程式碼

以下是 Aspose.Words for .NET 的「按 HTML 部分」功能的完整原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");


HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };


doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);
```

透過此程式碼，您將能夠使用 Aspose.Words for .NET 將 Word 文件分割為 HTML 格式的單獨部分。

現在您可以為初始文件的每個部分產生單獨的 HTML 文件。

## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 的按 HTML 部分功能將 Word 文件分割為 HTML 格式的單獨部分。透過遵循提供的原始程式碼，您可以為原始文件的每個部分產生單獨的 HTML 文件。

將文件劃分為多個部分可用於多種目的，例如建立網頁、提取特定內容或組織資訊。 Aspose.Words for .NET 提供了強大的 API，可讓您根據您的要求操作和自訂 Word 文件。

請隨意探索 Aspose.Words for .NET 提供的其他功能，以進一步增強您的文件處理能力並改善您的工作流程。

### 常見問題解答

#### 如何自訂 HTML 輸出格式？

Aspose.Words for .NET 提供了各種選項來自訂 HTML 輸出格式。您可以透過調整儲存選項來修改 HTML 文件的樣式、字體設定、圖像解析度和許多其他方面。有關可用選項及其使用方法的詳細信息，請參閱 Aspose.Words for .NET 文件。

#### 我可以根據不同的標準拆分文檔嗎？

是的，除了使用分節符作為分割標準之外，Aspose.Words for .NET 還提供其他選項，例如段落分隔符號、標題樣式或特定內容作為分割文件的標準。您可以根據您的要求選擇最合適的標準並相應地調整代碼。

#### 是否可以將文件分割為 HTML 以外的格式？

是的，Aspose.Words for .NET 支援將文件拆分為各種格式，包括 PDF、純文字、圖像等。您可以修改儲存選項以產生所需的輸出格式。有關可用格式以及如何在保存選項中指定它們的更多詳細信息，請參閱 Aspose.Words for .NET 文件。

#### 我可以同時分割多個文件嗎？

是的，您可以透過迭代文件集合併單獨為每個文件執行分割程式碼來同時將分割過程套用至多個文件。這使您可以有效地處理多個文件並為每個文件產生單獨的部分。

#### 如何將這些部分合併回單一文件？

Aspose.Words for .NET 也提供了將多個文件或部分合併回單一文件的方法。透過利用這些合併功能，您可以組合單獨產生的部分並建立統一的文件。有關如何合併文件或部分的更多信息，請參閱 Aspose.Words for .NET 文件。


