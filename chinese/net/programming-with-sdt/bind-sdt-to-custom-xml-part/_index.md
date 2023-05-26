---
title: 将 SDT 绑定到自定义 Xml 部件
linktitle: 将 SDT 绑定到自定义 Xml 部件
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将 SDT 绑定到自定义 Xml 部件。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

本教程演示如何使用 Aspose.Words for .NET 将结构化文档标签 (SDT) 绑定到自定义 Xml 部件。 SDT 允许您向 Word 文档添加结构化内容控件，而 CustomXmlParts 提供了一种存储与文档关联的自定义 XML 数据的方法。

## 先决条件
要学习本教程，您需要具备以下条件：

- 安装了 Aspose.Words for .NET 库。
- C# 和 XML 的基础知识。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建文档和 CustomXmlPart
创建一个新的实例`Document`类和一个`CustomXmlPart`存储自定义 XML 数据。自定义 XML 应采用有效的 XML 格式。在这个例子中，我们使用一个简单的 XML 字符串`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## 第 3 步：将 StructuredDocumentTag (SDT) 添加到文档
添加一个`StructuredDocumentTag`到文档作为内容控件。指定`SdtType`作为`PlainText`和`MarkupLevel`作为`Block`创建块级 SDT。

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## 第 4 步：为 SDT 设置 XML 映射
将 SDT 映射到`CustomXmlPart`通过使用`SetMapping`的方法`XmlMapping`财产。指定`CustomXmlPart`，用于定位所需 XML 节点的 XPath 表达式，以及必要时的命名空间前缀。在这个例子中，我们将 SDT 映射到`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## 第 5 步：保存文档
使用 将修改后的文档保存到指定目录`Save`方法。提供具有适当文件扩展名的所需文件名。在此示例中，我们将文档保存为“WorkingWithSdt.BindSDTtoCustomXmlPart.doc”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### 使用 Aspose.Words for .NET 的 Bind Sd Tto Custom Xml Part 示例源代码 

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

就是这样！您已经使用 Aspose.Words for .NET 成功地将 SDT 绑定到 Word 文档中的 CustomXmlPart。