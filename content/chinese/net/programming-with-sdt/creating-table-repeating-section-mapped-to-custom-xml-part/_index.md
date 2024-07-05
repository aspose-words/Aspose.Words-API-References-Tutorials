---
title: 创建映射到自定义 XML 部分的表重复部分
linktitle: 创建映射到自定义 XML 部分的表重复部分
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 创建一个表格，其中重复部分映射到 Word 文档中的 CustomXmlPart。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

本教程演示如何使用 Aspose.Words for .NET 创建表格，其中重复部分映射到 Word 文档中的自定义 XML 部分。重复部分允许您根据存储在自定义 XML 部分中的 XML 数据动态添加行。

## 先决条件
要遵循本教程，您需要满足以下条件：

- 已安装 Aspose.Words for .NET 库。
- 具备 C# 和 Word 文档文字处理的基本知识。

## 步骤 1：设置文档目录
首先设置文档目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`替换为您想要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：创建 Document 和 DocumentBuilder
创建一个新的实例`Document`类和一个`DocumentBuilder`构建文档的内容。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：将自定义 XML 数据添加到 CustomXmlPart
创建一个`CustomXmlPart`并向其中添加自定义 XML 数据。在此示例中，我们创建一个 XML 字符串，表示包含书名和作者的书籍集合。

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## 步骤 4：创建表和表结构
开始使用创建表`StartTable`方法`DocumentBuilder` 使用`InsertCell`和`Write`方法。

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## 步骤 5：创建映射到自定义 XML 的重复部分
创建一个`StructuredDocumentTag`和`SdtType.RepeatingSection`表示重复部分。使用`SetMapping`方法`XmlMapping`属性。在此示例中，我们将重复部分映射到`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## 步骤 6：创建重复部分项并添加单元格
创建一个`StructuredDocumentTag`和`SdtType.RepeatingSectionItem`表示重复部分项。将其作为子项附加到重复部分。

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

创建一个`Row`表示重复部分中的每个项目并将其附加到重复部分项目中。

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## 步骤 7：在重复部分中添加内容控件
创造`StructuredDocumentTag`具有`SdtType.PlainText`

 表示标题和作者内容控件。使用`SetMapping`方法`XmlMapping`属性。在此示例中，我们将标题控件映射到`/books[1]/book[1]/title[1]`和作者控制`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## 步骤 8：保存文档
使用将修改后的文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档保存为“WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### 使用 Aspose.Words for .NET 创建映射到自定义 XML 部分的表重复部分的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

就是这样！您已成功使用 Aspose.Words for .NET 创建了一个表格，其中的重复部分映射到 Word 文档中的 CustomXmlPart。