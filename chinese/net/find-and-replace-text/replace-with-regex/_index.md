---
title: 替换为正则表达式
linktitle: 替换为正则表达式
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中执行基于正则表达式的文本替换。
type: docs
weight: 10
url: /zh/net/find-and-replace-text/replace-with-regex/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的 Replace With Regex 函数。此功能允许您根据正则表达式定义的特定模式执行文本替换。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第 1 步：创建新文档

在开始使用正则表达式替换之前，我们需要使用 Aspose.Words for .NET 创建一个新文档。这可以通过实例化一个来完成`Document`目的：

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

## 步骤 3：配置查找和替换选项

现在我们将使用以下命令配置查找和替换选项`FindReplaceOptions`目的。在我们的示例中，我们使用默认选项：

```csharp
FindReplaceOptions options = new FindReplaceOptions();
```

## 第四步：用正则表达式替换

我们使用`Range.Replace`方法使用正则表达式执行文本替换。在我们的示例中，我们使用正则表达式“[s|m]ad" to find the words "sad" and "mad" and replace them with the word "bad":

```csharp
doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);
```

## 第五步：保存修改后的文档

最后，我们使用以下命令将修改后的文档保存到指定目录中`Save`方法：

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
```

### 使用 Aspose.Words for .NET 替换为正则表达式的示例源代码

以下是完整的示例源代码，演示如何使用 Aspose.Words for .NET 进行正则表达式替换：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	FindReplaceOptions options = new FindReplaceOptions();

	doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
  
```

## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 的 Replace With Regex 功能。我们按照分步指南创建文档、插入文本、使用正则表达式执行替换并保存修改后的文档。
