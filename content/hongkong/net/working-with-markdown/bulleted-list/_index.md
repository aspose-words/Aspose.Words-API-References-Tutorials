---
title: 項目符號列表
linktitle: 項目符號列表
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 逐步指南建立項目符號清單。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/bulleted-list/
---

在本教學中，我們將告訴您如何使用 Aspose.Words for .NET 建立項目符號清單。項目符號清單用於列出項目而不使用編號。

## 第 1 步：使用文件產生器

首先，我們將使用文件產生器將內容新增至文件。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：套用預設項目符號列表

我們可以使用文件建構器來套用預設的項目符號列表`ApplyBulletDefault`方法。

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## 第 3 步：自訂項目符號格式

我們可以透過存取屬性來自訂項目符號格式`ListFormat.List.ListLevels[0]`。在此範例中，我們使用破折號“-”作為項目符號。

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## 第 4 步：將項目新增到清單中

現在我們可以使用文件產生器將項目新增到項目符號清單中`Writeln`方法。

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## 步驟 5：從清單中刪除縮排

如果我們想要建立一個子列表，我們可以使用以下命令增加縮排`ListFormat.ListIndent()`方法。在此範例中，我們為項目 2a 和 2b 新增一個子清單。

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### 使用 Aspose.Words for .NET 的項目符號清單的範例原始碼


```csharp
//使用文件產生器將內容新增至文件。
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

恭喜！現在您已經學習如何使用 Aspose.Words for .NET 建立項目符號清單。

### 常見問題解答

#### Q：如何在 Markdown 中建立項目符號清單？

答：要在 Markdown 中建立項目符號列表，請以項目符號 (`-`, `*` ， 或者`+`)，後面跟一個空格。

#### Q：可以在 Markdown 中嵌套項目符號清單嗎？

答：是的，可以透過在每個嵌套列表項前面添加四個偏移空格來在 Markdown 中嵌套項目符號列表。

#### Q：如何自訂項目符號？

答：在標準 Markdown 中，項目符號是預先定義的。但是，某些 Markdown 編輯器可讓您使用特定擴充功能來自訂它們。

#### Q：Markdown 中的項目符號清單支援縮排嗎？

答：是的，Markdown 中的項目符號清單支援縮排。您可以使用空格或製表符新增左移。

#### Q：可以將連結或內嵌文字新增至清單項目嗎？

答：是的，您可以使用適當的 Markdown 語法添加連結或內聯文字以列出項目。
