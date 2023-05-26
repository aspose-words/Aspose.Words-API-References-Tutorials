---
title: 设置字体强调标记
linktitle: 设置字体强调标记
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中设置字体强调样式。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-font-emphasis-mark/
---

在本教程中，我们将向您展示如何使用 Aspose.Words for .NET 在 Word 文档中设置字体强调样式。字体强调用于突出显示文本中的某些单词或短语。

## 先决条件
在开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库

## 第一步：定义文档目录
首先将目录路径设置为 Word 文档的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建和自定义文档
创建一个实例`Document`类和相关联的`DocumentBuilder`构建文档内容。使用`Font.EmphasisMark`将字体强调样式设置为的属性`EmphasisMark.UnderSolidCircle`.然后使用`Write`和`Writeln`的方法`DocumentBuilder`添加具有指定字体强调的文本。

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## 第 3 步：保存文档
使用`Save`的方法`Document`使用适当的路径和文件名。

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### 使用 Aspose.Words for .NET 设置字体强调标记的示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## 结论
在本教程中，您学习了如何使用 Aspose.Words for .NET 在 Word 文档中设置字体强调样式。尝试不同的强调方式，并使用此功能突出显示文档中的单词或短语。
