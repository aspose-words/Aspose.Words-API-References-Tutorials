---
title: 断开 Word 文档中的前向链接
linktitle: 断开 Word 文档中的前向链接
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 断开 Word 文档中的前向链接。
type: docs
weight: 10
url: /zh/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET 是一个功能强大的库，它提供了各种功能，用于以编程方式处理 Microsoft Word 文档中的文字。它的一个有用功能是能够中断 Word 文档中的前向链接。在本教程中，我们将探索 C# 中的源代码，演示如何使用 Aspose.Words for .NET 中断 Word 文档中的前向链接。

## 步骤 1：C# 源代码预览

提供的 C# 源代码重点介绍 Aspose.Words for .NET 的“断开链接”功能。它展示了如何断开文档内 TextBox 形状中的链接。代码介绍了断开链接的不同场景，并提供了有关如何实现所需结果的清晰说明。

## 步骤 2：设置文档并创建 TextBox 形状

首先，我们需要设置文档并创建一个 TextBox 形状。以下代码初始化`Document`类并创建一个文本框形状：

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## 步骤 3：断开文本框中的前向链接

要打破文本框中的前向链接，我们可以使用`BreakForwardLink()`方法。此方法会断开与序列中下一个形状的链接。以下代码显示如何断开前向链接：

```csharp
textBox.BreakForwardLink();
```

## 步骤 4：通过设置空值来断开前向链接

或者，我们可以通过设置 TextBox 的`Next`财产`null`。这有效地删除了与下一个形状的连接。以下代码演示了这种方法：

```csharp
textBox. Next = null;
```

## 步骤 5：断开指向文本框的链接

在某些情况下，我们需要断开指向 TextBox 形状的链接。我们可以通过调用`BreakForwardLink()`方法`Previous`表单，这会断开与 TextBox 的链接。下面是如何断开此类链接的示例：

```csharp
textBox.Previous?.BreakForwardLink();
```

### 使用 Aspose.Words for .NET 断开链接的示例源代码

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

//中断前向链接。
textBox.BreakForwardLink();

//通过设置空值来断开前向链接。
textBox. Next = null;

//断开指向该文本框的链接。
textBox.Previous?.BreakForwardLink();
```

## 结论

恭喜！您现在已经学会了如何使用 .NET 的 Aspose.Words 库来中断 Word 文档中的重定向链接。按照本指南中的步骤，您可以设置文档、创建 TextBox 形状并使用不同的方法中断重定向链接。

### Word 文档中断开前向链接的常见问题解答

#### 问：使用 Aspose.Words for .NET 来中断 Word 文档中的重定向链接的库是什么？

答：要使用 Aspose.Words for .NET 打破 Word 文档中的重定向链接，所使用的库是 Aspose.Words for .NET。

#### 问：如何破坏文本框中的重定向链接？

答：要断开文本框中的前向链接，您可以使用`BreakForwardLink()`方法。此方法断开与序列中下一个形状的链接。

#### 问：如何通过设置空值来断开重定向链接？

答：或者，您可以通过设置`Next`TextBox 的属性`null`。这有效地消除了与下一个形状的连接。

#### 问：如何断开指向文本框的链接？

答：在某些情况下，您需要断开指向 TextBox 的链接。您可以通过调用`BreakForwardLink()`方法`Previous`表单，这会断开与文本框的链接。

#### 问：我们可以中断文本框以外元素上的重定向链接吗？

答：是的，使用 Aspose.Words for .NET 可以断开不同元素（如段落、表格、图像等）上的重定向链接。该过程可能因您想要断开链接的具体项目而异。