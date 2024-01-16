---
title: Word 文件中的亞洲版換行組
linktitle: Word 文件中的亞洲版換行組
second_title: Aspose.Words 文件處理 API
description: 了解如何透過 Aspose.Words for .NET 在 Word 文件中使用亞洲版式換行符號群組。
type: docs
weight: 10
url: /zh-hant/net/document-formatting/asian-typography-line-break-group/
---
在本教學中，我們將向您展示如何透過 Aspose.Words for .NET 在 Word 文件功能中使用亞洲版式換行符組。請按照以下步驟了解原始程式碼並套用格式變更。

## 第 1 步：載入文檔

首先，指定文檔的目錄並將包含亞洲版式的文檔載入到 Document 物件中。就是這樣：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## 第 2 步：亞洲版式設置

我們現在將為文件第一段配置亞洲版式設定。就是這樣：

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## 步驟 3：儲存文檔

插入文字輸入表單欄位後，使用以下命令將文件儲存到所需位置`Save`方法。確保提供適當的文件路徑：

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### 使用 Aspose.Words for .NET 的亞洲版換行群組的範例原始程式碼

以下是 Aspose.Words for .NET 的亞洲版換行組功能的完整原始碼：

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
透過此程式碼，您將能夠使用 Aspose.Words for .NET 應用亞洲版式換行符號群組。

## 結論

在本教學中，我們探索了 Aspose.Words for .NET 中的「亞洲版換行組」功能。透過配置`FarEastLineBreakControl`, `WordWrap`， 和`HangingPunctuation`的屬性`ParagraphFormat`，我們能夠控制 Word 文件中亞洲版式的換行行為。此功能對於處理亞洲字元以及確保具有混合語言內容的文件中的正確換行和自動換行非常有用。

### 常見問題解答

#### Q：Aspose.Words for .NET 中的「亞洲版式換行組」功能是什麼？

答：Aspose.Words for .NET 中的「亞洲版式換行組」功能可讓您控制 Word 文件中亞洲版式的換行行為。具體來說，它會影響在處理段落中的亞洲字元時換行和換行的方式。

#### Q：如何在 Aspose.Words for .NET 中啟用「亞洲版式換行群組」？

答：要啟用“亞洲版式換行組”，您需要配置`FarEastLineBreakControl`, `WordWrap`， 和`HangingPunctuation`的屬性`ParagraphFormat`您文件中的相關段落。環境`FarEastLineBreakControl`到`false`確保在換行方面亞洲字元的處理方式與拉丁字元類似。`WordWrap`設定`true`啟用亞洲版式的自動換行，以及`HangingPunctuation`設定`false`防止標點符號掛在亞洲文本中。

#### Q：我可以將「亞洲版式換行組」套用到文件中的特定段落嗎？

答：是的，您可以將「亞洲版式換行組」設定套用至 Word 文件中的特定段落。在範例程式碼中，設定應用於文件的第一段。您可以根據需要調整程式碼以定位其他段落，方法是透過`Paragraphs`文件中相關部分的集合。