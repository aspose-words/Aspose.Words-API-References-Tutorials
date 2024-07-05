---
title: 刪除線
linktitle: 刪除線
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 逐步指南套用刪除線文字樣式。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/strikethrough/
---


在此範例中，我們將引導您了解如何使用 Aspose.Words for .NET 套用刪除線文字樣式。刪除線文本用於指示文字已刪除或不再有效。

## 第 1 步：使用文件產生器

首先，我們將使用文件產生器將內容新增至文件。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：套用刪除線文字樣式

我們將透過設定啟用刪除線文字樣式`StrikeThrough`的財產`Font`反對`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## 步驟 3：新增刪除線文本

我們現在可以使用文檔生成器添加刪除線文本`Writeln`方法。

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### 使用 Aspose.Words for .NET 刪除文字的範例原始程式碼

```csharp
//使用文件產生器將內容新增至文件。
DocumentBuilder builder = new DocumentBuilder();

//將文字新增刪除線。
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

恭喜！現在您已經學習如何使用 Aspose.Words for .NET 應用程式刪除線文字樣式。

### 常見問題解答

#### Q：如何在 Aspose.Words 中新增刪除線文字？

答：要在 Aspose.Words 中新增刪除線文本，您可以使用`Font.StrikeThrough`的財產`Run`目的。您可以將此屬性設為`true`在特定文字中新增刪除線文字。例如，您可以使用`run.Font.StrikeThrough=true`將刪除線文字新增至`Run`目的。

#### Q：是否可以在同一段落的多段文字中新增刪除線文字？

答：是的，您可以使用多個文字在單一段落中的多個文字部分中新增刪除線文字。`Run`對象。您可以建立多個`Run`對象並設定`Font.StrikeThrough`財產給`true`對於每個對象，將刪除線文字新增至所需的文字部分。然後您可以使用以下命令將它們添加到段落中`Paragraph.AppendChild(run)`方法。

#### Q：我可以在 Aspose.Words 的表格或儲存格中的文字中新增刪除線文字嗎？

答：是的，您可以在 Aspose.Words 中的表格或儲存格中的文字中新增刪除線文字。您可以使用適當的方法跳到所需的儲存格或段落，然後使用以下命令套用刪除線文字格式：`Font.StrikeThrough`的財產`Run`或者`Paragraph`目的。