---
title: 斷開 Word 文件中的前向鏈接
linktitle: 斷開 Word 文件中的前向鏈接
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 斷開 Word 文件中的前向連結。
type: docs
weight: 10
url: /zh-hant/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET 是一個功能強大的函式庫，它以程式設計方式提供 Microsoft Word 文件的文字處理的各種功能。它的有用功能之一是能夠斷開 Word 文件中的前向連結。在本教學中，我們將探索 C# 原始程式碼，示範如何使用 Aspose.Words for .NET 斷開 Word 文件中的前向連結。

## 第 1 步：C# 原始碼預覽

提供的 C# 原始碼重點介紹 Aspose.Words for .NET 的「斷開連結」功能。它示範如何斷開文件內 TextBox 形狀中的連結。該程式碼呈現了斷開連結的不同場景，並提供了有關如何實現所需結果的清晰說明。

## 第 2 步：設定文件並建立文字方塊形狀

首先，我們需要設定文件並建立一個文字方塊形狀。下面的程式碼初始化了一個新的實例`Document`類別並建立一個文字方塊形狀：

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## 第 3 步：斷開 TextBox 中的前向鏈接

要斷開文字方塊中的前向鏈接，我們可以使用`BreakForwardLink()`方法。此方法會斷開與序列中下一個形狀的連結。以下程式碼顯示如何中斷前向連結：

```csharp
textBox.BreakForwardLink();
```

## 步驟 4：透過設定空值來中斷前向鏈接

或者，我們可以透過設定文字方塊來中斷前向連結`Next`財產給`null`。這有效地消除了與下一個形狀的連接。下面的程式碼演示了這種方法：

```csharp
textBox. Next = null;
```

## 第 5 步：斷開指向文字方塊的鏈接

在某些情況下，我們需要斷開通往 TextBox 形狀的連結。我們可以透過呼叫來實現這一點`BreakForwardLink()`方法上的`Previous`表單，這會破壞到 TextBox 的連結。以下是如何斷開此類連結的範例：

```csharp
textBox.Previous?.BreakForwardLink();
```

### 用於斷開與 Aspose.Words for .NET 的連結的範例原始碼

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

//斷開前向連結。
textBox.BreakForwardLink();

//透過設定空值來中斷前向連結。
textBox. Next = null;

//斷開指向此文字方塊的連結。
textBox.Previous?.BreakForwardLink();
```

## 結論

恭喜！現在您已經了解如何使用 .NET 的 Aspose.Words 程式庫斷開 Word 文件中的重定向連結。透過遵循本指南中的步驟，您可以使用不同的方法設定文件、建立文字方塊形狀並斷開重定向連結。

### Word 文件中斷開前向連結的常見問題解答

#### Q：使用 Aspose.Words for .NET 來斷開 Word 文件中的重定向連結的函式庫是什麼？

答：要使用 Aspose.Words for .NET 斷開 Word 文件中的重定向鏈接，所使用的庫是 Aspose.Words for .NET。

#### Q：如何斷開文字方塊中的重定向連結？

答：要斷開文字方塊中的前向鏈接，您可以使用`BreakForwardLink()`方法。此方法會斷開與序列中下一個形狀的連結。

#### Q：如何透過設定空值來中斷重定向連結？

答：或者，您可以透過設定來中斷重定向連結`Next`文字方塊的屬性為`null`。這有效地消除了與下一個形狀的連接。

#### Q：如何斷開通往文字方塊的連結？

答：在某些情況下，您需要斷開指向文字方塊的連結。您可以透過呼叫來實現這一點`BreakForwardLink()`方法上的`Previous`表單，這會破壞到 TextBox 的連結。

#### Q：我們可以斷開文字方塊以外的元素上的重定向連結嗎？

答：是的，使用Aspose.Words for .NET，可以斷開不同元素（如段落、表格、圖像等）上的重定向連結。特定項目。