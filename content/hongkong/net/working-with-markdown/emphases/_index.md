---
title: 重點
linktitle: 重點
second_title: Aspose.Words 文件處理 API
description: 了解如何透過 Aspose.Words for .NET 逐步指南使用強調符號（粗體和斜體）。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/emphases/
---

在此範例中，我們將解釋如何在 Aspose.Words for .NET 中使用強調符號。強調用於強調文字的某些部分，例如粗體和斜體。

## 第1步：文檔初始化

首先，我們將透過建立一個實例來初始化文檔`Document`班級。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## 第 2 步：使用文件產生器

接下來，我們將使用文件產生器將內容新增到文件中。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 3：新增帶有強調的文本

我們可以透過更改文件產生器的字型屬性來新增強調文字。在此範例中，我們使用粗體和斜體來強調文字的不同部分。

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## 步驟 4：儲存文檔

最後，我們可以將文件儲存為所需的格式。在此範例中，我們使用`.md`Markdown 格式的副檔名。

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

恭喜！現在您已經學習如何在 Aspose.Words for .NET 中使用強調符號。

### 使用 Aspose.Words for .NET 的 Emphases 範例原始碼


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### 常見問題解答

#### Q：如何使用 Markdown 突出顯示文字？

答：要使用 Markdown 突出顯示文本，只需用適當的符號包圍文本即可。使用`*`或者`_`對於斜體，`**`或者`__`為粗體，且`~~`用於刪除線。

#### Q：我們可以在同一篇文章中組合不同的亮點嗎？

答：是的，可以在同一文本中組合不同的亮點。例如，您可以使用兩者將單字加粗和斜體`**`和`*`圍繞這個詞。

#### Q：Markdown 中有哪些突出顯示選項？

答：Markdown 中可用的反白選項為斜體（`*`或者`_`）， 大膽的 （`**`或者`__`) 和刪除線 (`~~`）。

#### Q：如何處理文字包含 Markdown 用於突出顯示的特殊字元的情況？

答：如果您的文字包含 Markdown 用於突出顯示的特殊字符，您可以透過在它們前面加上`\`。例如，`\*`將顯示一個字面星號。

#### Q：我們可以使用 CSS 自訂突出顯示的外觀嗎？

答：Markdown 中的反白顯示通常使用瀏覽器的預設樣式呈現。如果將 Markdown 轉換為 HTML，則可以使用 CSS 規則自訂突出顯示的外觀。