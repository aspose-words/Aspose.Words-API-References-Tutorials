---
title: 断开链接
linktitle: 断开链接
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 断开 Word 文档中的链接。
type: docs
weight: 10
url: /zh/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET 是一个功能强大的库，它提供了以编程方式处理 Microsoft Word 文档的各种功能。它的一个有用功能是能够断开文档中的链接。在本教程中，我们将探索 C# 源代码，演示如何使用 Aspose.Words for .NET 断开链接。

## 第 1 步：C# 源代码预览

提供的 C# 源代码侧重于 Aspose.Words for .NET 的“断开链接”功能。它显示了如何断开文档内 TextBox 形状中的链接。该代码展示了断开链接的不同场景，并提供了有关如何实现预期结果的明确说明。

## 第 2 步：设置文档并创建文本框形状

首先，我们需要设置文档并创建一个文本框形状。下面的代码初始化了一个新的实例`Document`类并创建一个文本框形状：

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## 第 3 步：在 TextBox 中断开前向链接

要断开 TextBox 中的前向链接，我们可以使用`BreakForwardLink()`方法。此方法断开到序列中下一个形状的链接。以下代码显示了如何断开前向链接：

```csharp
textBox.BreakForwardLink();
```

## 第 4 步：通过设置空值来断开前向链接

或者，我们可以通过设置 TextBox 的`Next`财产给`null`.这有效地移除了与下一个形状的连接。以下代码演示了这种方法：

```csharp
textBox. Next = null;
```

## 第 5 步：断开指向文本框的链接

在某些情况下，我们需要断开指向 TextBox 形状的链接。我们可以通过调用`BreakForwardLink()`上的方法`Previous`窗体，它会断开到 TextBox 的链接。以下是如何断开此类链接的示例：

```csharp
textBox.Previous?.BreakForwardLink();
```

### 用于断开与 Aspose.Words for .NET 的链接的示例源代码

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

//断开前向链接。
textBox.BreakForwardLink();

//通过设置空值来断开前向链接。
textBox. Next = null;

//断开指向此文本框的链接。
textBox.Previous?.BreakForwardLink();
```

