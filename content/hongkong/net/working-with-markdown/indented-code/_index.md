---
title: 縮排程式碼
linktitle: 縮排程式碼
second_title: Aspose.Words 文件處理 API
description: 了解如何透過 Aspose.Words for .NET 逐步指南使用縮排程式碼。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/indented-code/
---

在此範例中，我們將解釋如何在 Aspose.Words for .NET 中使用縮排程式碼功能。縮排程式碼用於直觀地表示具有特定格式的程式碼區塊。

## 第 1 步：使用文件產生器

首先，我們將使用文件產生器將內容新增至文件。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 步驟 2：為縮排程式碼新增樣式

我們將使用以下命令為縮排程式碼新增自訂樣式`Styles.Add`的方法`Document`目的。在此範例中，我們為縮排程式碼建立一個名為「IndentedCode」的樣式。

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## 步驟 3：新增縮排程式碼

現在我們可以使用「IndentedCode」自訂樣式來新增縮排程式碼區塊。

```csharp
builder.Writeln("This is an indented code block");
```

### 使用 Aspose.Words for .NET 縮排程式碼的範例原始碼

```csharp
//使用文件產生器將內容新增至文件。
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

恭喜！現在您已經了解如何透過 Aspose.Words for .NET 使用縮排程式碼功能。


### 常見問題解答

#### Q：Markdown 中的縮排程式碼是什麼？

答：Markdown 中的縮排程式碼是一種用於在 Markdown 文件中顯示程式碼的格式化方法。它包括用空格或製表符縮進每行程式碼。

#### Q：如何在 Markdown 中使用縮排程式碼？

答：要在 Markdown 中使用縮排程式碼，請使用空格或製表符縮排每行程式碼。

#### Q：Markdown 中縮排程式碼的優點是什麼？

A：Markdown 中的縮排程式碼提高了程式碼的可讀性，讓讀者更容易理解。

#### Q：Markdown 中縮排程式碼和程式碼區塊有什麼差別？

答：縮排程式碼用於插入文字中的小程式碼片段，而程式碼區塊用於以單獨的格式顯示較大的程式碼片段。

#### Q：所有 Markdown 編輯器都支援 Markdown 中的縮排程式碼嗎？

答：Markdown 編輯器對縮排程式碼的支援可能會因 Markdown 編輯器而異。請檢查您的發布商的具體文件以確保確定。