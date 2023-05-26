---
title: 创建链接
linktitle: 创建链接
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中的文本框之间创建链接。
type: docs
weight: 10
url: /zh/net/working-with-textboxes/create-a-link/
---

## 第 1 步：设置文档并创建文本框形状

首先，我们需要设置文档并创建两个文本框形状。下面的代码初始化了一个新的实例`Document`类并创建两个文本框形状：

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;
```

## 第 2 步：在文本框之间创建链接

我们现在将使用`IsValidLinkTarget()`方法和`Next`第一个文本框的属性。

```csharp
if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```

这`IsValidLinkTarget()`方法检查第二个 TextBox 是否可以成为第一个 TextBox 链接的有效目标。如果验证成功，则`Next`第一个 TextBox 的属性设置为第二个 TextBox，从而在两者之间创建链接。

### 与 Aspose.Words for .NET 链接的示例源代码

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;

if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```