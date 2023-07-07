---
title: 富文本框内容控件
linktitle: 富文本框内容控件
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建富文本框内容控件，从而实现文本格式设置和样式设置。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/rich-text-box-content-control/
---

本教程演示如何使用 Aspose.Words for .NET 在 Word 文档中创建富文本框内容控件。富文本框内容控件允许用户使用各种样式和格式选项输入文本并设置文本格式。

## 先决条件
要学习本教程，您需要具备以下条件：

- 已安装 Aspose.Words for .NET 库。
- C# 和使用 Word 文档的基本知识。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`与要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建文档和 StructuredDocumentTag
创建一个新实例`Document`类和一个`StructuredDocumentTag`代表富文本框内容控件。指定`SdtType.RichText`作为类型和`MarkupLevel.Block`作为标记级别来创建块级富文本框。

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## 第 3 步：创建富文本内容并设置其格式
创建一个段落并运行以表示富文本内容。设置文本和格式选项，例如颜色、字体等。

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
使用以下命令将富文本框内容控件附加到文档正文`AppendChild`文档第一部分主体的方法。

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## 第 6 步：保存文档
使用以下命令将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档另存为“WorkingWithSdt.RichTextBoxContentControl.docx”。

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

就是这样！您已使用 Aspose.Words for .NET 在 Word 文档中成功创建了富文本框内容控件。