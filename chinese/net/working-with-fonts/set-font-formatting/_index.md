---
title: 设置字体格式
linktitle: 设置字体格式
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中设置字体格式并创建有吸引力的文档。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-font-formatting/
---
在本教程中，我们将向您展示如何使用 Aspose.Words for .NET 在 Word 文档中设置字体格式。您将学习如何应用粗体、颜色、斜体、字体、大小、间距和下划线等样式。

## 先决条件
在开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库

## 第一步：定义文档目录
首先将目录路径设置为 Word 文档的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档并设置格式
创建一个实例`Document`类和`DocumentBuilder`类来构建文档。使用`Font`的财产`DocumentBuilder`访问字体格式属性。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font. Bold = true;
font.Color = Color.DarkBlue;
font. Italic = true;
font.Name = "Arial";
font.Size = 24;
font. Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nicely formatted string.");
```

## 第 3 步：保存文档
使用`Save`使用应用的字体格式保存文档的方法。代替`"WorkingWithFonts.SetFontFormatting.docx"`使用所需的文件名。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");
```

### 使用 Aspose.Words for .NET 设置字体格式的示例源代码 
```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Bold = true;
font.Color = Color.DarkBlue;
font.Italic = true;
font.Name = "Arial";
font.Size = 24;
font.Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nice formatted string.");
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");

```

## 结论
恭喜！您现在知道如何使用 Aspose.Words for .NET 在 Word 文档中设置字体格式。您可以探索更多字体格式设置选项并创建个性化且有吸引力的 Word 文档。
