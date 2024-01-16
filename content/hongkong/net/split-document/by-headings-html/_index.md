---
title: 按標題 Html 拆分 Word 文檔
linktitle: 按標題 Html
second_title: Aspose.Words 文件處理 API
description: 逐步指南解釋 Aspose.Words for .NET 的分割 Word 文件 By Heading HTML 功能的 C# 原始碼
type: docs
weight: 10
url: /zh-hant/net/split-document/by-headings-html/
---
在本教學中，我們將引導您了解如何使用 Aspose.Words for .NET 的「按 HTML 標題」功能將 Word 文件分割為更小的部分。請按照以下步驟了解原始程式碼並根據 Heading 產生單獨的 HTML 文件。

## 第 1 步：載入文檔

首先，指定文檔的目錄並將文檔載入到 Document 物件中。就是這樣：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## 步驟 2：按 HTML 格式的標題劃分文檔

現在我們將設定儲存選項，根據 HTML 格式的標題將文件分割成更小的部分。就是這樣：

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
//將文件分割為較小的部分，在本例中按標題分隔。
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### 使用 Aspose.Words for .NET 的按標題 HTML 的範例原始程式碼

以下是 Aspose.Words for .NET 的「按 HTML 標題」功能的完整原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	//將文件拆分為較小的部分，在本例中按標題拆分。
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

透過此程式碼，您將能夠使用 Aspose.Words for .NET 根據標題將 Word 文件分割為更小的部分。然後您可以為每個部分產生單獨的 HTML 文件。

## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 的「按 HTML 標題」功能將 Word 文件分割為更小的部分。透過指定`DocumentSplitCriteria`作為`HeadingParagraph`在裡面`HtmlSaveOptions`，我們能夠根據原始文件中存在的標題產生單獨的 HTML 文件。

按標題拆分文件對於組織和管理內容非常有用，尤其是在具有多個部分的大型文件中。 Aspose.Words for .NET 提供了可靠且高效的解決方案來處理文件分割和產生各種格式的輸出。

請隨意探索 Aspose.Words for .NET 提供的其他功能和選項，以進一步增強您的文件處理能力並簡化您的工作流程。

### 常見問題解答

#### 如何使用 Aspose.Words for .NET 根據標題將 Word 文件分割為更小的部分？

若要根據標題拆分 Word 文檔，您可以使用 Aspose.Words for .NET 的「按 HTML 標題」功能。按照提供的源代碼並設置`DocumentSplitCriteria`到`HeadingParagraph`在裡面`HtmlSaveOptions`目的。這將在每個標題處將文件分成更小的部分。

#### 我可以將Word文檔拆分成哪些格式？

提供的原始程式碼示範了將 Word 文件拆分為 HTML 格式的較小部分。但是，Aspose.Words for .NET 支援各種輸出格式，包括 DOCX、PDF、EPUB 等。您可以修改程式碼並在中指定所需的輸出格式`HtmlSaveOptions`相應地反對。

#### 我可以選擇不同的標準來分割文件嗎？

是的，您可以根據您的要求選擇不同的文件拆分標準。 Aspose.Words for .NET 提供了多個標準選項，例如`HeadingParagraph`, `Page`, `Section`， 和更多。修改`DocumentSplitCriteria`財產在`HtmlSaveOptions`對象選擇適當的拆分標準。

#### 如何自訂分割部分的輸出 HTML？

 Aspose.Words for .NET 允許您通過在`HtmlSaveOptions`目的。您可以控制各個方面，例如 CSS 樣式、圖像、字體等。有關自訂 HTML 輸出的更多詳細信息，請參閱 Aspose.Words 文件。

#### 我可以根據多個條件拆分文檔嗎？

是的，您可以透過相應地組合條件選項來根據多個條件拆分文件。例如，您可以透過設定標題和頁面來拆分文檔`DocumentSplitCriteria`財產給`HeadingParagraph | Page`。這將在每個標題和每個頁面分割文檔，根據這兩個條件建立更小的部分。