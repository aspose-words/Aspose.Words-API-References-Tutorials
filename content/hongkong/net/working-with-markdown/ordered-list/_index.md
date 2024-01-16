---
title: 有序列表
linktitle: 有序列表
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 逐步指南建立有序清單。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/ordered-list/
---

在此範例中，我們將解釋如何透過 Aspose.Words for .NET 使用有序清單功能。有序列表可讓您用數字按順序組織項目。

## 第 1 步：使用文件產生器

首先，我們將使用文檔產生器來建立一個新文檔。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 2：套用有序列表格式

我們將使用文檔產生器來套用有序列表格式`ApplyBulletDefault`方法。我們還可以透過前往清單層級並設定我們想要的格式來自訂編號格式。

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## 第 3 步：將項目新增到清單中

我們可以使用文件產生器將項目新增到清單中`Writeln`方法。

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## 步驟 4：縮排列表

我們可以使用文件產生器來縮排列表`ListIndent`方法。

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## 第 5 步：儲存文檔

最後，我們可以將文件儲存為所需的格式。

### 使用 Aspose.Words for .NET 排序清單的範例原始碼

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

恭喜！現在您已經了解如何將有序清單功能與 Aspose.Words for .NET 一起使用。


### 常見問題解答

#### Q：如何在 Markdown 中建立有序列表？

答：要在 Markdown 中建立有序列表，請以數字開頭，後面接著句點 (`1.`, `2.`, `3.`)，後面跟一個空格。

#### Q：我們可以在 Markdown 中嵌套有序列表嗎？

答：是的，透過在每個嵌套列表項前面添加四個偏移空格，可以在 Markdown 中嵌套有序列表。

#### Q：如何自訂有序清單的編號？

答：在標準 Markdown 中，有序列表編號是自動產生的。但是，某些 Markdown 編輯器可讓您使用特定擴充功能來自訂它。

#### Q：Markdown 中的有序列表支援縮排嗎？

答：是的，Markdown 中的有序列表支援縮排。您可以使用空格或製表符新增左移。

#### Q：可以將連結或內嵌文字新增至清單項目嗎？

答：是的，您可以使用適當的 Markdown 語法添加連結或內聯文字以列出項目。