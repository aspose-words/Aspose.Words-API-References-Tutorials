---
title: 替换为字符串
linktitle: 替换为字符串
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将 Word 文档中的文本替换为字符串。
type: docs
weight: 10
url: /zh/net/find-and-replace-text/replace-with-string/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的 Replace With String 函数。该功能允许您根据Word文档中的特定字符串进行文本替换。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第 1 步：创建新文档

在开始使用字符串替换之前，我们需要使用 Aspose.Words for .NET 创建一个新文档。这可以通过实例化一个来完成`Document`目的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 步骤 2：将文本插入文档

一旦我们有了文档，我们就可以使用`DocumentBuilder`目的。在我们的示例中，我们使用`Writeln`插入短语“sad mad bad”的方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## 第 3 步：替换为字符串

我们使用`Range.Replace`方法用字符串替换文本。在我们的示例中，我们使用以下命令将所有出现的单词“sad”替换为“bad”`FindReplaceOptions`选项与`FindReplaceDirection.Forward`搜索方向：

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## 第四步：保存编辑好的文档

最后，我们使用以下命令将修改后的文档保存到指定目录中`Save`方法：

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### 使用 Aspose.Words for .NET 替换为字符串的示例源代码

以下是完整的示例源代码，说明如何使用 Aspose.Words for .NET 替换字符串：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 的 Replace With String 函数。我们按照分步指南创建文档、插入文本、替换为字符串并保存修改后的文档。
