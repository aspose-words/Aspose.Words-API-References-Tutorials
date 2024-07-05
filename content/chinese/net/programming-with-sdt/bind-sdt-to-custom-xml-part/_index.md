---
title: 将 SDT 绑定到自定义 Xml 部分
linktitle: 将 SDT 绑定到自定义 Xml 部分
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将 SDT 绑定到自定义 Xml 部分。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

本教程演示如何使用 Aspose.Words for .NET 将结构化文档标签 (SDT) 绑定到自定义 XML 部件。SDT 允许您将结构化内容控件添加到 Word 文档，而 CustomXmlParts 提供了一种存储与文档相关的自定义 XML 数据的方法。

## 先决条件
要遵循本教程，您需要满足以下条件：

- 已安装 Aspose.Words for .NET 库。
- C# 和 XML 的基本知识。

## 步骤 1：设置文档目录
首先设置文档目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`替换为您想要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：创建 Document 和 CustomXmlPart
创建一个新的实例`Document`类和一个`CustomXmlPart`存储自定义 XML 数据。自定义 XML 应为有效的 XML 格式。在此示例中，我们使用简单的 XML 字符串`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## 步骤 3：向文档添加 StructuredDocumentTag (SDT)
添加`StructuredDocumentTag`添加到文档中作为内容控件。指定`SdtType`作为`PlainText`和`MarkupLevel`作为`Block`创建块级 SDT。

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## 步骤 4：设置 SDT 的 XML 映射
将 SDT 映射到`CustomXmlPart`通过使用`SetMapping`方法`XmlMapping`属性。指定`CustomXmlPart`、XPath 表达式以定位所需的 XML 节点，以及命名空间前缀（如果需要）。在此示例中，我们将 SDT 映射到`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## 步骤 5：保存文档
使用将修改后的文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档保存为“WorkingWithSdt.BindSDTtoCustomXmlPart.doc”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### 使用 Aspose.Words for .NET 将 Sd Tto 绑定到自定义 Xml 部分的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

就是这样！您已成功使用 Aspose.Words for .NET 将 SDT 绑定到 Word 文档中的 CustomXmlPart。