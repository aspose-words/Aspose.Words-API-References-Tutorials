---
title: 內聯程式碼
linktitle: 內聯程式碼
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 逐步指南內嵌程式碼。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/inline-code/
---

在此範例中，我們將引導您了解如何使用 Aspose.Words for .NET 的內聯程式碼功能。內聯程式碼用於直觀地表示段落內的程式碼片段。

## 第 1 步：使用文件產生器

首先，我們將使用文件產生器將內容新增至文件。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 步驟 2：為內嵌程式碼新增樣式

我們將使用以下命令為內聯程式碼新增自訂樣式`Styles.Add`的方法`Document`目的。在此範例中，我們為具有預設反引號的內聯程式碼建立一個名為「InlineCode」的樣式。

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## 第 3 步：新增內聯代碼

現在我們可以使用「InlineCode」自訂樣式來新增內聯代碼。在此範例中，我們新增了兩段具有不同數量反引號的文字。

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### 使用 Aspose.Words for .NET 進行內聯程式碼的範例原始程式碼

```csharp
//使用文件產生器將內容新增至文件。
DocumentBuilder builder = new DocumentBuilder();

//缺少反引號數，預設使用 1 個反引號。
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

//將有 3 個反引號。
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

恭喜！現在您已經了解如何使用 Aspose.Words for .NET 的內嵌程式碼功能。


### 常見問題解答

#### Q：如何在 Aspose.Words 中使用內聯代碼？

答：要在 Aspose.Words 中使用內聯代碼，您可以使用適當的標籤將要格式化為內聯代碼的文字包圍起來。例如，您可以使用`<code>`或者`<kbd>`標籤包圍要格式化為內聯代碼的文字。

#### Q：是否可以在 Aspose.Words 中指定內聯代碼字體或顏色？

答：是的，您可以在Aspose.Words中指定內聯代碼的字體或顏色。您可以使用`Font.Name`和`Font.Color`的屬性`Run`物件設定內聯代碼的字體和顏色。例如，您可以使用`run.Font.Name = "Courier New"`指定內聯程式碼的字型和`run.Font.Color = Color.Blue`指定顏色。

#### Q：我可以在包含其他文字元素的段落中使用內聯程式碼嗎？

答：是的，您可以在包含其他文字元素的段落中使用內聯代碼。您可以建立多個`Run`物件來表示段落的不同部分，然後使用內聯代碼標記僅將特定部分格式化為內聯代碼。然後您可以使用以下命令將它們添加到段落中`Paragraph.AppendChild(run)`方法。