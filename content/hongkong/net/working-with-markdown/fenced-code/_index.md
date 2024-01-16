---
title: 圍欄代碼
linktitle: 圍欄代碼
second_title: Aspose.Words 文件處理 API
description: 了解如何透過 Aspose.Words for .NET 逐步指南使用隔離程式碼功能。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/fenced-code/
---

在此範例中，我們將引導您了解如何透過 Aspose.Words for .NET 使用隔離程式碼功能。圍欄代碼用於表示具有特定格式的程式碼區塊。

## 第 1 步：使用文件產生器

首先，我們將使用文件產生器將內容新增至文件。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 步驟 2： 新增受防護代碼的樣式

我們將使用以下命令為受防護的程式碼添加自訂樣式`Styles.Add`的方法`Document`目的。在此範例中，我們為受保護的程式碼建立一個名為「FencedCode」的樣式。

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## 第 3 步：新增不含資訊的防護代碼

現在我們可以使用「FencedCode」自訂樣式來新增一個沒有資訊字串的隔離程式碼區塊。

```csharp
builder.Writeln("This is an fenced code");
```

## 步驟 4： 新增帶有資訊字串的防護代碼

我們還可以使用另一種自訂樣式來添加帶有一串資訊的圍欄程式碼區塊。在此範例中，我們將建立一個名為「FencedCode.C#」的樣式來表示 C# 程式碼區塊。

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### 使用 Aspose.Words for .NET 的 Fenced Code 的範例原始碼

```csharp
//使用文件產生器將內容新增至文件。
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### 常見問題解答

#### Q：Markdown 中的分隔程式碼是什麼？

答：Markdown 中的分隔程式碼是一種用於在 Markdown 文件中顯示程式碼的格式化方法。它包括使用特定分隔符號建立程式碼。

#### Q：Markdown 中分隔程式碼有什麼好處？

答：Markdown 中的分隔程式碼提高了程式碼的可讀性，讓讀者更容易理解。它還允許在某些 Markdown 編輯器中保留語法突出顯示。

#### Q：Markdown 中分隔程式碼和縮排程式碼有什麼差別？

答：分隔程式碼使用特定的分隔符號將程式碼括起來，而縮排程式碼則涉及使用空格或製表符縮排每行程式碼。

#### Q：所有 Markdown 編輯器都支援 Markdown 中的分隔程式碼嗎？

答：Markdown 中對分隔程式碼的支援可能會因 Markdown 編輯器而異。請檢查您的發布商的具體文件以確保確定。

