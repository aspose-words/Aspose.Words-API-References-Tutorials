---
title: 在替换处插入文档
linktitle: 在替换处插入文档
second_title: Aspose.Words 文档处理 API
description: 通过我们详细的分步指南，了解如何使用 Aspose.Words for .NET 将一个 Word 文档无缝插入到另一个文档中。非常适合希望简化文档处理的开发人员。
type: docs
weight: 10
url: /zh/net/clone-and-combine-documents/insert-document-at-replace/
---
## 介绍

嘿，文档大师！您是否曾经发现自己陷入了代码困境，试图找出如何将一个 Word 文档无缝插入到另一个文档中？不要害怕，因为今天我们将深入了解 Aspose.Words for .NET 的世界，让这项任务变得轻而易举。我们将详细介绍如何使用这个强大的库在查找和替换操作期间的特定点插入文档。准备好成为 Aspose.Words 向导了吗？让我们开始吧！

## 先决条件

在我们开始编写代码之前，您需要做好以下几件事：

-  Visual Studio：确保您的计算机上安装了 Visual Studio。如果您还没有，您可以从以下位置下载[这里](https://visualstudio.microsoft.com/).
- Aspose.Words for .NET：您需要 Aspose.Words 库。您可以从[阿斯普斯网站](https://releases.aspose.com/words/net/).
- 基本 C# 知识：对 C# 和 .NET 的基本了解将帮助您遵循本教程。

好吧，抛开这些，让我们开始编写一些代码吧！

## 导入命名空间

首先，我们需要导入必要的命名空间来使用 Aspose.Words。这就像在开始项目之前收集所有工具一样。在 C# 文件顶部添加这些 using 指令：

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

现在我们已经具备了先决条件，让我们将这个过程分解为几个小步骤。每一步都至关重要，将使我们更接近我们的目标。

## 第 1 步：设置文档目录

首先，我们需要指定存储文档的目录。这就像大型表演之前的舞台搭建。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`与您的目录的路径。这是您的文档生存和呼吸的地方。

## 第2步：加载主文档

接下来，我们加载要插入另一个文档的主文档。将此视为我们的主要舞台，所有动作都将在其中发生。

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

此代码从指定目录加载主文档。

## 步骤 3：设置查找和替换选项

为了找到我们想要插入文档的特定位置，我们使用查找和替换功能。这就像使用地图来找到我们新添加的确切位置一样。

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

在这里，我们将方向设置为向后并指定接下来定义的自定义回调处理程序。

## 步骤4：执行替换操作

现在，我们告诉主文档查找特定的占位符文本并将其替换为空，同时使用自定义回调插入另一个文档。

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

此代码执行查找和替换操作，然后保存更新的文档。

## 第 5 步：创建自定义替换回调处理程序

我们的自定义回调处理程序就是神奇发生的地方。该处理程序将定义在查找和替换操作期间如何执行文档插入。

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        //在包含匹配文本的段落之后插入文档。
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        //删除包含匹配文本的段落。
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

在这里，我们加载要插入的文档，然后调用辅助方法来执行插入。

## 第 6 步：定义插入文档方法

我们的最后一个难题是在指定位置实际插入文档的方法。

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		//循环该节主体中的所有块级节点，
		//然后克隆并插入不是节的最后一个空段落的每个节点。
		foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
		foreach (Node srcNode in srcSection.Body)
		{
			if (srcNode.NodeType == NodeType.Paragraph)
			{
				Paragraph para = (Paragraph)srcNode;
				if (para.IsEndOfSection && !para.HasChildNodes)
					continue;
			}

			Node newNode = importer.ImportNode(srcNode, true);

			destinationParent.InsertAfter(newNode, insertionDestination);
			insertionDestination = newNode;
		}
	}
	else
	{
		throw new ArgumentException("The destination node should be either a paragraph or table.");
	}
}
```

此方法负责从要插入的文档中导入节点并将它们放置在主文档中的正确位置。

## 结论

现在你就拥有了！使用 Aspose.Words for .NET 将一个文档插入另一个文档的综合指南。通过执行这些步骤，您可以轻松地自动执行文档组装和操作任务。无论您是要构建文档管理系统还是只是需要简化文档处理工作流程，Aspose.Words 都是您值得信赖的助手。

## 常见问题解答

### 什么是 Aspose.Words for .NET？
Aspose.Words for .NET 是一个功能强大的库，用于以编程方式操作 Word 文档。它允许您轻松创建、修改、转换和处理 Word 文档。

### 我可以一次插入多个文档吗？
是的，您可以修改回调处理程序以通过迭代文档集合来处理多个插入。

### 有免费试用吗？
绝对地！您可以从以下位置下载免费试用版[这里](https://releases.aspose.com/).

### 如何获得 Aspose.Words 支持？
您可以通过访问获得支持[Aspose.Words 论坛](https://forum.aspose.com/c/words/8).

### 我可以保留插入文档的格式吗？
是的`NodeImporter`类允许您指定将节点从一个文档导入到另一文档时如何处理格式。