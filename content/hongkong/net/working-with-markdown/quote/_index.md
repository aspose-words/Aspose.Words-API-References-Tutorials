---
title: 引用
linktitle: 引用
second_title: Aspose.Words 文件處理 API
description: 了解如何透過 Aspose.Words for .NET 逐步指南使用參考。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/quote/
---

在此範例中，我們將解釋如何使用 Aspose.Words for .NET Quote 的參考功能，透過以特殊邊框包圍文字部分來突出顯示它們。

## 第 1 步：使用文件產生器

首先，我們將使用文件產生器將內容新增至文件。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：使用預設引文樣式

我們將使用名為「引用」的預設段落樣式將引用格式套用到文字。

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## 步驟 3：為嵌套層級建立樣式

我們可以使用以下命令為巢狀層級建立樣式`Styles.Add`的方法`Document`目的。在此範例中，我們建立一個名為「Quote1」的樣式來表示巢狀報價等級。

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### 使用 Aspose.Words for .NET 進行引用的範例原始碼


```csharp
//使用文件產生器將內容新增至文件。
DocumentBuilder builder = new DocumentBuilder();

//預設情況下，文件儲存第一級的區塊引用樣式。
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

//透過樣式繼承為巢狀層級建立樣式。
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

恭喜！現在您已經了解如何使用 Aspose.Words for .NET 的引用功能。


### 常見問題解答

#### Q：Markdown 中的引用是什麼？

答：Markdown 中的引用是一種突出顯示其他來源的文本段落或引用著名引用的方法。

#### Q：如何在 Markdown 使用引號？

答：要在 Markdown 中使用引用，請將引用文字括在尖括號中 (`>`）。引文的每一行必須以 V 形開頭。

#### Q：Markdown 引號支援屬性嗎？

答：Markdown 引用不支援特定屬性。它們只是透過引用文字的格式來突出顯示。

#### Q：可以在 Markdown 嵌入引號嗎？

答：是的，可以透過增加額外的尖括號（`>`）。