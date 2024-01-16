---
title: 固定文字標題
linktitle: 固定文字標題
second_title: Aspose.Words 文件處理 API
description: 透過 Aspose.Words for .NET 逐步指南了解如何使用 Setext 標題來格式化文件。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/setext-heading/
---

在本教學中，我們將引導您了解如何將 Setext 標題功能與 Aspose.Words for .NET 一起使用。 Setext 標題是在 Markdown 文件中格式化標題的另一種方法。

## 第 1 步：使用文件產生器

首先，我們將使用文件產生器將內容新增至文件。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：使用 Settext 標題樣式

我們將使用預設的「標題 1」段落樣式在文件中建立 1 級標題。

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## 第三步：重設樣式

我們重設了先前套用的字體樣式，以避免段落之間出現任何不必要的樣式組合。

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## 第 4 步：自訂 Setext 標題級別

我們可以透過基於現有標題樣式新增新的段落樣式來自訂 Setext 標題層級。在此範例中，我們基於「Heading 1」樣式建立「SetextHeading1」樣式，以表示 Setext 格式中的 1 級標題。

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## 第 5 步：儲存文檔

最後，我們可以將文件儲存為所需的格式。

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### 使用 Aspose.Words for .NET 的 Setext 標題的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//使用文件產生器將內容新增至文件。
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

//重設上一段的樣式，以不合併段落之間的樣式。
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

//重設上一段的樣式，以不合併段落之間的樣式。
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

//如果基本段落的標題等級大於 2，Setex 標題等級將重設為 2。
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### 常見問題解答

#### Q：什麼是 Setext Markdown 標頭？

答：Setext Markdown 標題是另一種在 Markdown 文件中建立標題的方法。它使用下劃線字元（= 或 -）來指示不同層級的標題。

#### Q：如何使用 Setext Markdown 標題？

答：要使用 Setext Markdown 標題，請將底線放在標題文字下方。對於 1 級標題使用等號 (=)，對於 2 級標題使用連字號 (-)。

#### Q：使用 Setext Markdown 標頭有什麼限制嗎？

答：Setext Markdown 標題在標題層次結構方面有限制，並且在視覺上不像標準 Markdown 標題那麼明顯。

#### Q：我可以自訂 Setext Markdown 標題的外觀嗎？

答：在標準 Markdown 中，無法自訂 Setext Markdown 標題的外觀。它們具有基於所使用的下劃線字元的預定義外觀。

#### Q：所有 Markdown 編輯器都支援 Setext Markdown 標頭嗎？

答：不同 Markdown 編輯器對 Setext Markdown 標頭的支援可能有所不同。請檢查您的發布商的具體文件以確保確定。