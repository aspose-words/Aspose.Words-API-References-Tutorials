---
title: 重启列表号码
linktitle: 重启列表号码
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中重新开始列表编号。这份详细的 2000 字指南涵盖了您需要了解的所有内容，从设置到高级自定义。
type: docs
weight: 10
url: /zh/net/working-with-list/restart-list-number/
---
## 介绍

您是否希望使用 Aspose.Words for .NET 掌握 Word 文档中的列表操作技巧？好吧，您来对地方了！在本教程中，我们将深入探讨重新启动列表编号，这是一项巧妙的功能，可将您的文档自动化技能提升到一个新的水平。系好安全带，让我们开始吧！

## 先决条件

在我们进入代码之前，让我们确保您拥有所需的一切：

1.  Aspose.Words for .NET：您需要安装 Aspose.Words for .NET。如果您尚未安装，您可以[点击下载](https://releases.aspose.com/words/net/).
2. 开发环境：确保您有一个合适的开发环境，如 Visual Studio。
3. C# 基础知识：对 C# 的基本了解将帮助您跟随本教程。

## 导入命名空间

首先，让我们导入必要的命名空间。这些对于访问 Aspose.Words 功能至关重要。

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
using System.Drawing;
```

现在，让我们将这个过程分解成易于遵循的步骤。我们将介绍从创建列表到重新开始编号的所有内容。

## 步骤 1：设置文档和生成器

在开始操作列表之前，您需要一个文档和一个 DocumentBuilder。DocumentBuilder 是您向文档添加内容的首选工具。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：创建并自定义您的第一个列表

接下来，我们将根据模板创建一个列表并自定义其外观。在此示例中，我们使用带括号的阿拉伯数字格式。

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

在这里，我们将字体颜色设置为红色，并将文本右对齐。

## 步骤 3：将项目添加到您的第一个列表

准备好列表后，就可以添加一些项目了。DocumentBuilder 的`ListFormat.List`属性有助于将列表格式应用于文本。

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## 步骤 4：重新开始列表编号

要重新使用列表并重新开始编号，您需要创建原始列表的副本。这样您就可以单独修改新列表。

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

在此示例中，新列表从数字 10 开始。

## 步骤 5：将项目添加到新列表

和之前一样，将项目添加到新列表中。这将演示列表从指定数字重新开始。

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## 步骤 6：保存文档

最后，将您的文档保存到指定的目录。

```csharp
builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
```

## 结论

使用 Aspose.Words for .NET 重新开始 Word 文档中的列表编号非常简单且非常有用。无论您是生成报告、创建结构化文档，还是只需要更好地控制列表，此技术都可以满足您的需求。

## 常见问题解答

### 除了 NumberArabicParenthesis 之外，我可以使用其他列表模板吗？

当然！Aspose.Words 提供各种列表模板，如项目符号、字母、罗马数字等。您可以选择最适合您需求的模板。

### 如何更改列表级别？

您可以通过修改`ListLevels`属性。例如，`list1.ListLevels[1]`将引用列表的第二级。

### 我可以从任意数字重新开始编号吗？

是的，你可以使用`StartAt`列表级别的属性。

### 不同列表级别可以采用不同的格式吗？

确实如此！每个列表级别都可以有自己的格式设置，例如字体、对齐方式和编号样式。

### 如果我想从先前的列表继续编号而不是重新开始，该怎么办？

如果要继续编号，则无需创建列表的副本。只需继续将项目添加到原始列表中即可。


