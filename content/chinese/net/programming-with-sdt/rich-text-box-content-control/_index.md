---
title: 富文本框内容控件
linktitle: 富文本框内容控件
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建富文本框内容控件，以实现文本格式和样式设置。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/rich-text-box-content-control/
---

本教程演示如何使用 Aspose.Words for .NET 在 Word 文档中创建富文本框内容控件。富文本框内容控件允许用户使用各种样式和格式选项输入和格式化文本。

## 先决条件
要遵循本教程，您需要满足以下条件：

- 已安装 Aspose.Words for .NET 库。
- 具备 C# 和 Word 文档文字处理的基本知识。

## 步骤 1：设置文档目录
首先设置文档目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`替换为您想要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：创建文档和 StructuredDocumentTag
创建一个新的实例`Document`类和一个`StructuredDocumentTag`表示富文本框内容控件。指定`SdtType.RichText`作为类型和`MarkupLevel.Block`作为标记级别来创建块级富文本框。

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## 步骤 3：创建并格式化富文本内容
创建段落并运行以表示富文本内容。设置文本和格式选项，如颜色、字体等。

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## 步骤 4：将富文本内容添加到内容控件
将包含富文本内容的段落添加到`ChildNodes`富文本框内容控件的集合。

```csharp
sdtRichText.ChildNodes.Add(para);
```

## 步骤 5：将内容控件附加到文档
使用将富文本框内容控件附加到文档正文`AppendChild`文档第一部分主体的方法。

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## 步骤 6：保存文档
使用将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档保存为“WorkingWithSdt.RichTextBoxContentControl.docx”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### 使用 Aspose.Words for .NET 的富文本框内容控件的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

就是这样！您已成功使用 Aspose.Words for .NET 在 Word 文档中创建了富文本框内容控件。