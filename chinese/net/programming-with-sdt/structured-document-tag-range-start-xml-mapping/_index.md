---
title: 结构化文档标记范围起始 Xml 映射
linktitle: 结构化文档标记范围起始 Xml 映射
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中为结构化文档标记范围设置 XML 映射。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

本教程介绍如何使用 Aspose.Words for .NET 在 Word 文档中设置结构化文档标记范围的 XML 映射。 XML 映射允许您在内容控件中显示 XML 数据源的特定部分。

## 先决条件
要学习本教程，您需要具备以下条件：

- 已安装 Aspose.Words for .NET 库。
- C# 和 Word 文档文字处理的基础知识。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`与文档所在目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载文档并创建 XML 部件
使用以下命令加载 Word 文档`Document`构造函数，将文档的路径作为参数传递。创建一个 XML 部件，其中包含要在结构化文档标记内显示的数据。

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## 步骤 3：为结构化文档标签设置 XML 映射
检索从文档开始的结构化文档标签范围。然后，设置结构化文档标记的 XML 映射，以使用 XPath 表达式显示自定义 XML 部分的特定部分。

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## 步骤 4：保存文档
使用命令将修改后的文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档另存为“WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### 使用 Aspose.Words for .NET 进行结构化文档标记范围开始 Xml 映射的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	//构造一个包含数据的 XML 部件并将其添加到文档的 CustomXmlPart 集合中。
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	//创建一个 StructuredDocumentTag，它将在文档中显示 CustomXmlPart 的内容。
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	//如果我们为 StructuredDocumentTag 设置映射，
	//它只会显示 XPath 指向的 CustomXmlPart 的一部分。
	//此 XPath 将指向 CustomXmlPart 的第一个“<root>”元素的内容第二个“<text>”元素。
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

就是这样！您已使用 Aspose.Words for .NET 在 Word 文档中成功设置了结构化文档标记范围起始的 XML 映射。