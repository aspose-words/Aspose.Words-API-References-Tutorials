---
title: 删除部分
linktitle: 删除部分
second_title: Aspose.Words for .NET API 参考
description: 在本教程中，学习如何使用 Aspose.Words for .NET 从 Word 文档中删除特定部分。
type: docs
weight: 10
url: /zh/net/working-with-section/delete-section/
---

在本教程中，我们将向您展示如何使用 .NET 的 Aspose.Words 库删除 Word 文档的特定部分。删除部分对于重新排列或删除文档的特定部分很有用。我们将带您一步一步地帮助您理解和实现您的 .NET 项目中的代码。

## 先决条件
在开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库

## 第 1 步：创建文档和构造函数
首先，我们将创建一个实例`Document`类和相关联的`DocumentBuilder`构建文档的构造函数。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：添加内容和部分
接下来，我们将使用`DocumentBuilder`向文档添加内容和部分的构造函数。在此示例中，我们添加了两行文本和两个部分。

```csharp
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello2");
doc.AppendChild(new Section(doc));
```

## 第 3 步：删除特定部分
要删除文档的特定部分，我们将使用`RemoveAt`文档的方法`Sections`集合，指定要删除的部分的索引。

```csharp
doc.Sections.RemoveAt(0);
```

### 使用 Aspose.Words for .NET 的 Delete Section 示例源代码 

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.Writeln("Hello1");
	doc.AppendChild(new Section(doc));
	builder.Writeln("Hello2");
	doc.AppendChild(new Section(doc));
	doc.Sections.RemoveAt(0);

```

## 结论
在本教程中，我们了解了如何使用 Aspose.Words for .NET 从 Word 文档中删除特定部分。删除部分允许您重新排列或删除文档的特定部分。您可以根据自己的具体需要随意自定义和使用此功能。

