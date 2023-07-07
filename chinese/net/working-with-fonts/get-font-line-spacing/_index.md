---
title: 获取字体行距
linktitle: 获取字体行距
second_title: Aspose.Words for .NET API 参考
description: 在本教程中，了解如何使用 Aspose.Words for .NET 获取 Word 文档中的字体行距。
type: docs
weight: 10
url: /zh/net/working-with-fonts/get-font-line-spacing/
---
在本教程中，我们将告诉您如何使用 .NET 的 Aspose.Words 库获取 Word 文档中的字体行距。字体行距定义文本行之间的垂直间距。我们将逐步指导您理解并实现 .NET 项目中的代码。

## 先决条件
开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库

## 第 1 步：创建新文档和文档生成器
首先，我们将通过实例化创建一个新文档`Document`类和文档构建器通过实例化`DocumentBuilder`班级。

```csharp
//创建一个新文档
Document doc = new Document();

//创建文档生成器
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第2步：配置字体
接下来，我们将通过设置来配置字体`Name`文档生成器的属性。

```csharp
//配置字体
builder.Font.Name = "Calibri";
```

## 步骤 3：向文档添加文本
我们现在将使用文档生成器将格式化文本添加到文档中。

```csharp
//添加文本到文档
builder. Writen("qText");
```

## 第四步：获取字体行距
现在我们将访问`Font`文档第一段的对象并检索该值`LineSpacing`财产。

```csharp
//获取字体的行距
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### 使用 Aspose.Words for .NET 获取字体行间距的示例源代码 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## 结论
在本教程中，我们了解了如何使用 Aspose.Words for .NET 获取 Word 文档中的字体行距。字体行距对于控制文本行之间的垂直间距很重要。请随意使用此功能来自定义文档中文本的外观。

### 常见问题解答

#### 问：如何更改Word文档中特定文本的行距？

答：使用Aspose.Words，您可以轻松更改Word文档中特定文本的行距。使用 API 选择所需的文本并通过指定适当的值来调整行间距。

#### 问：是否可以在 Word 文档中应用精确的行间距？

答：是的，Aspose.Words 允许您在 Word 文档中应用精确的行间距。您可以使用 API 指定行间距的精确值。

#### 问：如何调整整个Word文档的行距？

答：使用Aspose.Words，您可以轻松调整整个Word文档的行间距。使用 API 提供的方法指定整个文档所需的行距。

#### 问：Aspose.Words 支持多行间距吗？

答：是的，Aspose.Words 支持 Word 文档中的多行间距。您可以为文本行设置多个间距，例如正常间距的 1.5 倍或 2 倍。

#### 问：调整行距时如何避免行重叠问题？

答：为避免调整行间距时出现行重叠问题，请务必选择合适的间距值。还要测试文档的最终渲染，以确保文本保持可读且格式良好。