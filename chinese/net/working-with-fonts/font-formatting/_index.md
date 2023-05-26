---
title: 字体格式
linktitle: 字体格式
second_title: Aspose.Words for .NET API 参考
description: 在本教程中，学习如何使用 Aspose.Words for .NET 格式化 Word 文档中的字体。
type: docs
weight: 10
url: /zh/net/working-with-fonts/font-formatting/
---

在本教程中，我们将向您介绍如何使用 .NET 的 Aspose.Words 库在 Word 文档中进行字体格式化。字体格式让您可以自定义文本的外观，包括大小、粗体、颜色、字体、下划线等。我们将带您一步一步地帮助您理解和实现您的 .NET 项目中的代码。

## 先决条件
在开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库

## 第一步：定义文档目录
首先，您需要将目录路径设置为您的 Word 文档所在的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建新文档和文档生成器
接下来，我们将通过实例化`Document`类和文档生成器通过实例化`DocumentBuilder`班级。

```csharp
//创建一个新文档
Document doc = new Document();

//创建文档生成器
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：配置字体格式
现在我们将访问`Font`文档生成器的对象并配置字体格式属性，如大小、粗体、颜色、字体、下划线等。

```csharp
//访问字体
Font font = builder.Font;

//配置字体格式
font.Size = 16;
font. Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
```

## 第 4 步：向文档添加文本
接下来，我们将使用文档生成器将一些格式化文本添加到文档中。

```csharp
//向文档添加文本
builder.Write("Example text.");
```

## 第 5 步：保存文档
最后，我们将保存包含字体格式的文档。

```csharp
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

### 使用 Aspose.Words for .NET 进行字体格式化的示例源代码 
```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
builder.Write("Sample text.");
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

## 结论
在本教程中，我们了解了如何使用 Aspose.Words for .NET 在 Word 文档中进行字体格式化。字体格式允许您自定义文档中文本的外观。随意使用此功能来创建有吸引力的专业文档。