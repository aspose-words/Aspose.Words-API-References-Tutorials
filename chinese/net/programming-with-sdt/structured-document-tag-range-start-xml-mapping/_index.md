---
title: 结构化文档标记范围开始 Xml 映射
linktitle: 结构化文档标记范围开始 Xml 映射
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中开始为结构化文档标记范围设置 XML 映射。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

本教程解释了如何使用 Aspose.Words for .NET 为 Word 文档中开始的结构化文档标签范围设置 XML 映射。 XML 映射允许您在内容控件中显示 XML 数据源的特定部分。

## 先决条件
要学习本教程，您需要具备以下条件：

- 安装了 Aspose.Words for .NET 库。
- C# 的基本知识和使用 Word 文档。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用文档所在目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载文档并创建 XML 部分
使用`Document`构造函数，将文档的路径作为参数传递。创建一个 XML 部件，其中包含要在结构化文档标记中显示的数据。

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## 第 3 步：为结构化文档标签设置 XML 映射
从文档开始检索结构化文档标签范围。然后，为结构化文档标记设置 XML 映射，以使用 XPath 表达式显示自定义 XML 部分的特定部分。

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## 第 4 步：保存文档
使用 将修改后的文档保存到指定目录`Save`方法。提供具有适当文件扩展名的所需文件名。在此示例中，我们将文档保存为“WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Structured Document Tag Range Start Xml Mapping using Aspose.Words for .NET 的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	//构造一个包含数据的 XML 部件并将其添加到文档的 CustomXmlPart 集合中。
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	//创建一个 StructuredDocumentTag，它将在文档中显示我们的 CustomXmlPart 的内容。
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	//如果我们为 StructuredDocumentTag 设置一个映射，
	//它只会显示 XPath 指向的 CustomXmlPart 的一部分。
	//此 XPath 将指向我们的 CustomXmlPart 的第一个“<root>”元素的第二个“<text>”元素的内容。
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功地为 Word 文档中开始的结构化文档标签范围设置了 XML 映射。