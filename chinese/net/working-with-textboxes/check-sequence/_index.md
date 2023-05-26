---
title: 检查顺序
linktitle: 检查顺序
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 检查 Word 文档中文本框的顺序。
type: docs
weight: 10
url: /zh/net/working-with-textboxes/check-sequence/
---

## 第 1 步：设置文档并创建文本框形状

首先，我们需要设置文档并创建一个文本框形状。下面的代码初始化了一个新的实例`Document`类并创建一个文本框形状：

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## 第 2 步：检查 TextBox 序列

我们现在将使用检查文本框的顺序`if`状况。提供的源代码包含三个单独的条件，用于检查 TextBox 相对于前后形状的位置。

## 第 3 步：检查序列头：

```csharp
if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}
```

如果 TextBox 有下一个形状 (`Next`) 但没有以前的形状 (`Previous`), 这意味着它是序列的头部。将显示消息“序列的头部”。

## 第 4 步：检查序列的中间部分：

```csharp
if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}
```

如果 TextBox 具有 Next 形状 (`Next`) 和一个以前的形状 (`Previous`), 这表明它在序列的中间。将显示消息“序列的中间”。

## 第 5 步：序列结束的验证：

```csharp
if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

如果 TextBox 没有下一个形状 (`Next`) 但有一个以前的形状 (`Previous`)，这意味着它是序列的结尾。将显示消息“序列结束”。

### 使用 Aspose.Words for .NET 验证序列的示例源代码

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}

if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}

if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```