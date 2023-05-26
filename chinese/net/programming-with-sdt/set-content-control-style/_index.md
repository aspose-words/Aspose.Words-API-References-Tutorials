---
title: 设置内容控件样式
linktitle: 设置内容控件样式
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 设置 Word 文档中内容控件的样式，并应用一致的格式。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/set-content-control-style/
---

本教程解释了如何使用 Aspose.Words for .NET 在 Word 文档中设置内容控件的样式。您可以将预定义或自定义样式应用于内容控件以获得一致的格式。

## 先决条件
要学习本教程，您需要具备以下条件：

- 安装了 Aspose.Words for .NET 库。
- C# 的基本知识和使用 Word 文档。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用文档所在目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载文档并检索内容控件
使用`Document`构造函数，将文档的路径作为参数传递。从文档中检索所需的内容控件。在此示例中，我们假设内容控件是文档中的第一个结构化文档标记。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 第 3 步：检索样式并应用于内容控件
从文档的样式集合中检索所需的样式。在此示例中，我们通过使用检索“报价”样式`StyleIdentifier.Quote`.然后，将检索到的样式分配给`Style`结构化文档标签的属性。

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## 第 4 步：保存文档
使用 将修改后的文档保存到指定目录`Save`方法。提供具有适当文件扩展名的所需文件名。在本例中，我们将文档保存为“WorkingWithSdt.SetContentControlStyle.docx”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### 使用 Aspose.Words for .NET 设置内容控件样式的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功设置了 Word 文档中内容控件的样式。