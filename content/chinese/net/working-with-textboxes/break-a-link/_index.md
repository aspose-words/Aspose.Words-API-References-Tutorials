---
title: 断开 Word 文档中的前向链接
linktitle: 断开 Word 文档中的前向链接
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 断开 Word 文档中的前向链接。
type: docs
weight: 10
url: /zh/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET 是一个功能强大的库，它以编程方式提供 Microsoft Word 文档的文字处理的各种功能。它的有用功能之一是能够断开 Word 文档中的前向链接。在本教程中，我们将探索 C# 源代码，演示如何使用 Aspose.Words for .NET 断开 Word 文档中的前向链接。

## 第 1 步：C# 源代码预览

提供的 C# 源代码重点介绍 Aspose.Words for .NET 的“断开链接”功能。它演示了如何断开文档内 TextBox 形状中的链接。该代码呈现了断开链接的不同场景，并提供了有关如何实现所需结果的清晰说明。

## 第 2 步：设置文档并创建文本框形状

首先，我们需要设置文档并创建一个文本框形状。下面的代码初始化了一个新的实例`Document`类并创建一个文本框形状：

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## 第 3 步：断开 TextBox 中的前向链接

要断开文本框中的前向链接，我们可以使用`BreakForwardLink()`方法。此方法会断开与序列中下一个形状的链接。以下代码显示了如何中断前向链接：

```csharp
textBox.BreakForwardLink();
```

## 步骤 4：通过设置空值来中断前向链接

或者，我们可以通过设置文本框来中断前向链接`Next`财产给`null`。这有效地消除了与下一个形状的连接。下面的代码演示了这种方法：

```csharp
textBox. Next = null;
```

## 第 5 步：断开指向文本框的链接

在某些情况下，我们需要断开通向 TextBox 形状的链接。我们可以通过调用来实现这一点`BreakForwardLink()`方法上的`Previous`表单，这会破坏到 TextBox 的链接。以下是如何断开此类链接的示例：

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

//通过设置空值来中断前向链接。
textBox. Next = null;

//断开指向此文本框的链接。
textBox.Previous?.BreakForwardLink();
```

## 结论

恭喜！您现在已经了解了如何使用 .NET 的 Aspose.Words 库断开 Word 文档中的重定向链接。通过遵循本指南中的步骤，您可以设置文档、创建文本框形状以及使用不同的方法断开重定向链接。

### Word 文档中断开前向链接的常见问题解答

#### 问：使用 Aspose.Words for .NET 来断开 Word 文档中的重定向链接的库是什么？

答：要使用 Aspose.Words for .NET 断开 Word 文档中的重定向链接，所使用的库是 Aspose.Words for .NET。

#### 问：如何断开文本框中的重定向链接？

答：要断开文本框中的前向链接，您可以使用`BreakForwardLink()`方法。此方法会断开与序列中下一个形状的链接。

#### 问：如何通过设置空值来中断重定向链接？

答：或者，您可以通过设置来中断重定向链接`Next`文本框的属性为`null`。这有效地消除了与下一个形状的连接。

#### 问：如何断开通向文本框的链接？

答：在某些情况下，您需要断开指向文本框的链接。您可以通过调用来实现这一点`BreakForwardLink()`方法上的`Previous`表单，这会破坏到 TextBox 的链接。

#### 问：我们可以断开文本框以外的元素上的重定向链接吗？

答：是的，使用 Aspose.Words for .NET，可以断开不同元素（如段落、表格、图像等）上的重定向链接。该过程可能会有所不同，具体取决于您要断开链接的特定项目。