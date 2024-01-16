---
title: 水平線
linktitle: 水平線
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 逐步指南插入水平線。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/horizontal-rule/
---

在此範例中，我們將向您展示如何將水平標尺功能與 Aspose.Words for .NET 一起使用。水平線用於在視覺上分隔文件的各個部分。

## 第 1 步：使用文件產生器

首先，我們將使用文件產生器將內容新增至文件。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 步驟 2：插入水平線

我們可以使用插入水平線`InsertHorizontalRule`文檔生成器的方法。

```csharp
builder. InsertHorizontalRule();
```

## 使用 Aspose.Words for .NET 進行水平標尺的範例原始程式碼

```csharp
//使用文件產生器將內容新增至文件。
DocumentBuilder builder = new DocumentBuilder();

//插入水平線。
builder.InsertHorizontalRule();
```

恭喜！現在您已經了解如何將水平標尺功能與 Aspose.Words for .NET 一起使用。


### 常見問題解答

#### Q：如何在 Markdown 中建立水平標尺？

答：要在 Markdown 中建立水平標尺，您可以在空白行上使用下列符號之一：三個星號（\***）、三個破折號（\---)，或三個底線(\___）。

#### Q：我可以在 Markdown 中自訂水平標尺的外觀嗎？

答：在標準 Markdown 中，無法自訂水平標尺的外觀。但是，一些進階 Markdown 編輯器和擴充功能提供了額外的自訂功能。

#### Q：所有 Markdown 編輯器都支援水平標尺嗎？

答：是的，大多數流行的 Markdown 編輯器都支援水平標尺。但是，最好檢查特定供應商的文件以確保其受支援。

#### Q：我還可以在 Markdown 中創建哪些其他元素？

答：除了水平標尺之外，您還可以在 Markdown 中建立標題、段落、清單、連結、圖像、表格等。