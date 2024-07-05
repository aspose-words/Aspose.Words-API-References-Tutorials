---
title: 结构化文档标签范围开始 XML 映射
linktitle: 结构化文档标签范围开始 XML 映射
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 为 Word 文档中的结构化文档标签范围开始设置 XML 映射。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

本教程介绍如何使用 Aspose.Words for .NET 在 Word 文档中为结构化文档标记范围开始设置 XML 映射。XML 映射允许您在内容控件中显示 XML 数据源的特定部分。

## 先决条件
要遵循本教程，您需要满足以下条件：

- 已安装 Aspose.Words for .NET 库。
- 具备 C# 和 Word 文档文字处理的基本知识。

## 步骤 1：设置文档目录
首先设置文档目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档所在目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：加载文档并创建 XML 部分
使用加载 Word 文档`Document`构造函数，将路径作为参数传递到文档。创建一个 XML 部分，其中包含要在结构化文档标记内显示的数据。

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## 步骤 3：设置结构化文档标签的 XML 映射
从文档中检索结构化文档标签范围开始。然后，设置结构化文档标签的 XML 映射，以使用 XPath 表达式显示自定义 XML 部分的特定部分。

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## 步骤 4：保存文档
使用将修改后的文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档保存为“WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### 使用 Aspose.Words for .NET 进行结构化文档标签范围开始 XML 映射的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	//构造一个包含数据的 XML 部分并将其添加到文档的 CustomXmlPart 集合中。
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	//创建一个 StructuredDocumentTag，它将在文档中显示我们的 CustomXmlPart 的内容。
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	//如果我们为 StructuredDocumentTag 设置映射，
	//它将仅显示 XPath 指向的 CustomXmlPart 的一部分。
	//该 XPath 将指向我们的 CustomXmlPart 的第一个“<root>”元素的第二个“<text>”元素的内容。
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

就是这样！您已成功使用 Aspose.Words for .NET 在 Word 文档中为结构化文档标签范围开始设置 XML 映射。