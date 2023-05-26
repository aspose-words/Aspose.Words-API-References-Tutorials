---
title: 配置内容链接
linktitle: 配置内容链接
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 设置文档内容链接的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-properties/configuring-link-to-content/
---

在本教程中，我们将引导您通过 C# 源代码设置与 Aspose.Words for .NET 内容的链接。此功能允许您链接到文档中的特定内容。

## 第 1 步：项目设置

首先，在您喜欢的 IDE 中创建一个新的 C# 项目。确保在您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：创建文档和构造函数

在这一步中，我们将创建一个新文档并初始化构造函数。使用以下代码：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：创建书签

现在我们将在文档中创建一个书签。使用以下代码创建一个包含文本的书签：

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

此代码创建一个名为“MyBookmark”的书签并在其中添加一些文本。

## 第 4 步：设置内容链接

现在我们将使用文档属性配置指向内容的链接。使用以下代码添加和检索内容链接：

```csharp
//获取文档中所有自定义属性的列表。
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
//添加内容绑定属性。
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

此代码添加名为“Bookmark”的内容相关属性，书签为“MyBookmark”。然后，它检索与内容相关的属性信息，例如链接状态、链接源和属性值。

### 使用 Aspose.Words for .NET 配置内容链接的示例源代码

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	//从文件中检索所有自定义文档属性的列表。
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	//添加链接到内容属性。
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

您现在已经学习了如何使用 Aspose.Words for .NET 配置指向文档内容的链接。按照本教程中提供的分步指南，您可以轻松地创建和配置指向您自己文档中特定内容的链接。