---
title: 应用段落样式
linktitle: 应用段落样式
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 应用段落样式。
type: docs
weight: 10
url: /zh/net/document-formatting/apply-paragraph-style/
---

在本教程中，我们将引导您了解如何使用 Aspose.Words for .NET 应用段落样式。请按照以下步骤了解源代码并应用段落样式。

## 第 1 步：创建并配置文档

首先，创建一个新文档和关联的 DocumentBuilder 对象。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第2步：配置段落样式

我们现在将使用内置样式标识符配置段落样式。就是这样：

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## 第 3 步：添加内容

我们将向该段落添加内容。就是这样：

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### 使用 Aspose.Words for .NET 应用段落样式的示例源代码

以下是 Aspose.Words for .NET 的“应用段落样式”功能的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

通过此代码，您将能够使用 Aspose.Words for .NET 应用段落样式。

