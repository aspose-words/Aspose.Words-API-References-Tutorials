---
title: 设置内容控件样式
linktitle: 设置内容控件样式
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 设置 Word 文档中内容控件的样式，应用一致的格式。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/set-content-control-style/
---

本教程介绍如何使用 Aspose.Words for .NET 设置 Word 文档中内容控件的样式。您可以将预定义或自定义样式应用于内容控件以实现一致的格式。

## 先决条件
要遵循本教程，您需要满足以下条件：

- 已安装 Aspose.Words for .NET 库。
- 具备 C# 和 Word 文档文字处理的基本知识。

## 步骤 1：设置文档目录
首先设置文档目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档所在目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：加载文档并检索内容控件
使用加载 Word 文档`Document`构造函数，将路径作为参数传递给文档。从文档中检索所需的内容控件。在此示例中，我们假设内容控件是文档中的第一个结构化文档标签。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 步骤 3：检索样式并应用于内容控件
从文档的样式集合中检索所需的样式。在此示例中，我们使用以下方法检索“Quote”样式`StyleIdentifier.Quote`。然后，将检索到的样式分配给`Style`结构化文档标签的属性。

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## 步骤 4：保存文档
使用将修改后的文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档保存为“WorkingWithSdt.SetContentControlStyle.docx”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### 使用 Aspose.Words for .NET 设置内容控制样式的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

就这样！您已成功使用 Aspose.Words for .NET 设置了 Word 文档中内容控件的样式。