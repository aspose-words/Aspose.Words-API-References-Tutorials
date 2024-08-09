---
title: 删除 PDF 文件中的注释
linktitle: 删除 PDF 文件中的注释
second_title: Aspose.Words 文档处理 API
description: 通过我们的分步指南了解如何使用 Aspose.Words for .NET 从 PDF 文件中删除注释。
type: docs
weight: 10
url: /zh/net/working-with-revisions/remove-comments-in-pdf/
---
## 介绍

嗨，各位开发人员！处理 PDF 文件时，您是否曾发现自己被一堆乱七八糟的注释所困扰？您并不孤单。无论是同行评审还是协作项目，注释有时都会使您的文档变得杂乱。幸运的是，Aspose.Words for .NET 提供了一种无缝的方式来删除这些令人讨厌的注释。今天，我们将逐步介绍该过程。所以，系好安全带，让我们深入 Aspose.Words 的世界吧！

## 先决条件

在开始之前，请确保您已准备好所需的一切：

1.  Aspose.Words for .NET：确保已安装该库。你可以从以下网址下载[这里](https://releases.aspose.com/words/net/).
2. 开发环境：任何与 .NET 兼容的 IDE，例如 Visual Studio。
3. C# 基础知识：如果您熟悉 C# 编程基础知识，这将很有帮助。
4. 带有注释的文档：我们需要一个带有注释的 Word 文档 (.docx) 来进行测试。

如果您已经准备好了，让我们进入激动人心的部分！

## 导入命名空间

首先，我们需要导入必要的命名空间。这使我们能够使用 Aspose.Words 提供的类和方法。

```csharp
using Aspose.Words;
using Aspose.Words.Layout;
```

这些命名空间使我们能够访问所需的文档处理和布局选项。

## 步骤 1：加载文档

让我们首先加载包含评论的文档。此文档应存储在您有权访问的目录中。


```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Revisions.docx");
```

在此代码片段中，替换`"YOUR DOCUMENT DIRECTORY"`替换为文档目录的实际路径。我们正在加载一个名为`Revisions.docx`.

## 步骤 2：隐藏 PDF 中的注释

接下来，我们需要隐藏注释，这样它们就不会出现在文档的 PDF 版本中。Aspose.Words 使这变得非常简单。

```csharp
//隐藏 PDF 中的注释。
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

这行代码告诉 Aspose.Words 在呈现文档时隐藏注释。

## 步骤 3：将文档保存为 PDF

最后，我们将修改后的文档保存为 PDF。此步骤可确保我们的注释在输出文件中删除。


```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

这里，我们将文档以新名称保存到同一个目录，表示 PDF 版本中的注释已被删除。

## 结论

就这样！只需几个简单的步骤，我们就成功地使用 Aspose.Words for .NET 从 PDF 文件中删除了注释。这个功能强大的库简化了文档操作，使处理原本繁琐的任务变得轻而易举。

记住，熟能生巧。所以，继续在你的文档中尝试一下。你会惊讶地发现，没有那些杂乱无章的评论，你的 PDF 看起来会更加干净、专业。

## 常见问题解答

### 如果我想保留一些评论但删除其他评论怎么办？
您可以在设置之前直接在文档中操作注释节点来选择性地隐藏注释`CommentDisplayMode`.

### 除了 PDF 之外，我可以将 Aspose.Words 用于其他文件格式吗？
当然！Aspose.Words 支持多种文件格式，包括 DOCX、TXT、HTML 等。

### Aspose.Words 有免费试用版吗？
是的，您可以免费试用[这里](https://releases.aspose.com/).

### 如果在使用 Aspose.Words 时遇到问题怎么办？
您可以访问[支持论坛](https://forum.aspose.com/c/words/8)以获得有关您可能遇到的任何问题的帮助。

### 如何购买 Aspose.Words 的许可证？
您可以从购买许可证[这里](https://purchase.aspose.com/buy).