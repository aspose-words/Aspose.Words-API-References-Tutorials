---
title: 获取字体行间距
linktitle: 获取字体行间距
second_title: Aspose.Words for .NET API 参考
description: 在本教程中，学习如何使用 Aspose.Words for .NET 在 Word 文档中获取字体行间距。
type: docs
weight: 10
url: /zh/net/working-with-fonts/get-font-line-spacing/
---
在本教程中，我们将告诉您如何使用 .NET 的 Aspose.Words 库获取 Word 文档中的字体行间距。字体行间距定义文本行之间的垂直间距。我们将带您一步一步地帮助您理解和实现您的 .NET 项目中的代码。

## 先决条件
在开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库

## 第 1 步：创建新文档和文档生成器
首先，我们将通过实例化`Document`类和文档生成器通过实例化`DocumentBuilder`班级。

```csharp
//创建一个新文档
Document doc = new Document();

//创建文档生成器
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第二步：配置字体
接下来，我们将通过设置来配置字体`Name`文档生成器的属性。

```csharp
//配置字体
builder.Font.Name = "Calibri";
```

## 第 3 步：向文档添加文本
我们现在将使用文档生成器将格式化文本添加到文档中。

```csharp
//向文档添加文本
builder. Writen("qText");
```

## 第 4 步：获取字体行间距
现在我们将访问`Font`文档第一段的对象并检索的值`LineSpacing`财产。

```csharp
//获取字体的行间距
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
在本教程中，我们了解了如何使用 Aspose.Words for .NET 获取 Word 文档中的字体行间距。字体行间距对于控制文本行之间的垂直间距很重要。您可以随意使用此功能来自定义文档中文本的外观。
