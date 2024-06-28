---
title: 設定尾註選項
linktitle: 設定尾註選項
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中設定尾註選項。帶有範例原始程式碼的分步教程。
type: docs
weight: 10
url: /zh-hant/net/working-with-footnote-and-endnote/set-endnote-options/
---

在本逐步教學中，我們將指導您如何使用 Aspose.Words for .NET 在 Word 文件中設定尾註選項。我們將解釋提供的 C# 原始程式碼，並向您展示如何在您自己的專案中實現它。

首先，請確保您已在開發環境中安裝並設定了 Aspose.Words for .NET。如果您還沒有這樣做，請從以下位置下載並安裝該程式庫[Aspose.Releases]https://releases.aspose.com/words/net/。

## 第 1 步：初始化文檔對象

首先，初始化`Document`透過提供來源文檔的路徑來物件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## 第 2 步：初始化 DocumentBuilder 對象

接下來，初始化`DocumentBuilder`對文件執行操作的物件：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：新增文字和尾註

使用`Write`的方法`DocumentBuilder`新增文字文字的對象，以及`InsertFootnote`插入尾註的方法：

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## 第 4 步：設定尾註選項

訪問`EndnoteOptions`文檔的屬性來修改尾註選項。在本例中，我們將重啟規則設定為在每個頁面上重新啟動，並將位置設定為該部分的結尾：

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## 第 5 步：儲存文檔

最後儲存修改後的文件：

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 在 Word 文件中成功設定尾註選項。

### 使用 Aspose.Words for .NET 設定尾註選項的範例原始碼

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

請隨意在您自己的專案中使用此程式碼，並根據您的特定要求進行修改。

### 常見問題解答

#### Q：如何在 Aspose.Words 中設定尾註樣式？

答：要在 Aspose.Words 中設定尾註樣式，您可以使用`EndnoteOptions`類和`SeparatorNoteTextStyle`財產。您可以使用此屬性指定尾註的字體樣式、大小、顏色等。

#### Q：是否可以自訂文件中尾註的編號？

答：是的，可以自訂文件中尾註的編號。您可以使用`RestartRule`和`NumberStyle`的屬性`EndnoteOptions`類別來定義特定的重新啟動規則和編號樣式。

#### Q：如何在文件中放置尾註？

答：要在文件中放置尾註，您可以使用`Position`的財產`EndnoteOptions`班級。您可以指定尾註是否應放置在每頁的底部、每個部分的末尾或文件的末尾。

#### Q：我可以自訂尾註編號格式嗎？

答：是的，您可以在 Aspose.Words 中自訂尾註編號的格式。使用`NumberFormat`的財產`EndnoteOptions`class 來設定所需的格式，如阿拉伯數字、羅馬數字、字母等。

#### Q：是否可以在文件各部分之間繼續進行尾註編號？

答：是的，可以在文件各部分之間繼續進行尾註編號。使用`RestartRule`的財產`EndnoteOptions`類別並將其設定為`RestartContinuous`允許在各節之間繼續編號。