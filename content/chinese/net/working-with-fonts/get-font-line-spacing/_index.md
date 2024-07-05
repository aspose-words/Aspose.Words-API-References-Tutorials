---
title: 获取字体行距
linktitle: 获取字体行距
second_title: Aspose.Words 文档处理 API
description: 在本教程中，学习如何使用 Aspose.Words for .NET 获取 Word 文档中的字体行距。
type: docs
weight: 10
url: /zh/net/working-with-fonts/get-font-line-spacing/
---
在本教程中，我们将告诉您如何使用 .NET 的 Aspose.Words 库获取 Word 文档中的字体行距。字体行距定义文本行之间的垂直空间。我们将逐步指导您理解和实现 .NET 项目中的代码。

## 先决条件
开始之前，请确保您拥有以下物品：
- 具备 C# 编程语言的工作知识
- 项目中安装的 .NET Aspose.Words 库

## 步骤 1：创建新文档和文档生成器
首先，我们将通过实例化创建一个新文档`Document`通过实例化`DocumentBuilder`班级。

```csharp
//创建新文档
Document doc = new Document();

//创建文档生成器
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：配置字体
接下来，我们将通过设置`Name`文档生成器的属性。

```csharp
//配置字体
builder.Font.Name = "Calibri";
```

## 步骤 3：向文档添加文本
我们现在将使用文档生成器向文档添加格式化的文本。

```csharp
//向文档添加文本
builder. Writen("qText");
```

## 步骤 4：获取字体行距
现在我们将访问`Font`文档第一段的对象并检索`LineSpacing`财产。

```csharp
//获取字体的行距
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### 使用 Aspose.Words for .NET 获取字体行距的示例源代码 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## 结论
在本教程中，我们了解了如何使用 Aspose.Words for .NET 获取 Word 文档中的字体行距。字体行距对于控制文本行之间的垂直间距非常重要。您可以随意使用此功能自定义文档中文本的外观。

### 常见问题解答

#### 问：如何更改 Word 文档中特定文本的行距？

答：使用 Aspose.Words，您可以轻松更改 Word 文档中特定文本的行距。使用 API 选择所需的文本，并通过指定适当的值来调整行距。

#### 问：是否可以在 Word 文档中应用行间精确间距？

答：是的，Aspose.Words 允许您在 Word 文档中应用行间距的精确值。您可以使用 API 为行间距指定精确值。

#### 问：如何调整整个 Word 文档的行距？

A: 使用 Aspose.Words，您可以轻松调整整个 Word 文档的行距。使用 API 提供的方法指定整个文档所需的行距。

#### 问：Aspose.Words 支持多行间距吗？

A: 是的，Aspose.Words 支持 Word 文档中的多行间距。您可以为文本行设置多行间距，例如 1.5 倍或 2 倍正常间距。

#### 问：调整行距时如何避免线条重叠问题？

答：为避免在调整行距时出现行重叠问题，请务必选择适当的间距值。还要测试文档的最终呈现效果，以确保文本仍然可读且格式正确。