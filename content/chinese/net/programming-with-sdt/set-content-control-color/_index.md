---
title: 设置内容控件颜色
linktitle: 设置内容控件颜色
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 设置 Word 文档中内容控件的颜色并自定义其外观。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/set-content-control-color/
---

本教程介绍如何使用 Aspose.Words for .NET 设置 Word 文档中内容控件的颜色。您可以通过更改内容控件的颜色来自定义其外观。

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

## 步骤 3：设置内容控件颜色
通过分配一个来设置内容控件的颜色`Color`价值`Color`结构化文档标签的属性。在此示例中，我们将颜色设置为红色。

```csharp
sdt.Color = Color.Red;
```

## 步骤 4：保存文档
使用将修改后的文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档保存为“WorkingWithSdt.SetContentControlColor.docx”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### 使用 Aspose.Words for .NET 设置内容控制颜色的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

就这样！您已成功使用 Aspose.Words for .NET 设置了 Word 文档中内容控件的颜色。