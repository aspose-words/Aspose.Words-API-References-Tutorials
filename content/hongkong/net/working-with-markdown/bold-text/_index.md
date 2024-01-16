---
title: 加粗字體
linktitle: 加粗字體
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 逐步指南將文字加粗。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/bold-text/
---

在此範例中，我們將告訴您如何使用 Aspose.Words for .NET 將文字加粗。粗體文字使其更加明顯並更加突出。

## 第 1 步：使用文件產生器

首先，我們將使用文件產生器將內容新增至文件。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：粗體文本

我們可以透過設定文檔產生器的`Font.Bold`財產給`true`.

```csharp
builder.Font.Bold = true;
```

## 步驟 3：為文件新增內容

現在我們可以使用文件建構器方法為文件添加內容，例如`Writeln`，這會添加一行文字。

```csharp
builder.Writeln("This text will be bold");
```

## 使用 Aspose.Words for .NET 的粗體文字範例原始程式碼


```csharp
//使用文件產生器將內容新增至文件。
DocumentBuilder builder = new DocumentBuilder();

//將文字設為粗體。
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

恭喜！現在您已經了解如何使用 Aspose.Words for .NET 將文字加粗。


### 常見問題解答

#### Q：如何在 Aspose.Words 中將文字設為粗體？

答：要在 Aspose.Words 中將文字設為粗體，您可以使用`Font.Bold`的財產`Run`目的。您可以將此屬性設為`true`將特定文字加粗。例如，您可以使用`run.Font.Bold=true`將裡面的文字加粗`Run`目的。

#### Q：是否可以將同一段落中的多段文字加粗？

答：是的，您可以使用多個將單一段落中的多段文字加粗`Run`對象。您可以建立多個`Run`對象並設定`Font.Bold`財產給`true`對於每個對象，將所需的文字部分加粗。然後您可以使用以下命令將它們添加到段落中`Paragraph.AppendChild(run)`方法。

#### Q：我可以將 Aspose.Words 中表格或儲存格中的文字加粗嗎？

答：是的，您可以在 Aspose.Words 中將表格或儲存格中的文字加粗。您可以使用適當的方法導覽至所需的儲存格或段落，然後使用`Font.Bold`的財產`Run`或者`Paragraph`目的。