---
title: 复选框类型内容控制
linktitle: 复选框类型内容控制
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建复选框类型内容控件。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/check-box-type-content-control/
---

本教程介绍如何使用 Aspose.Words for .NET 在 Word 文档中创建复选框类型内容控件。复选框内容控件允许用户在文档中选择或清除复选框。

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

## 步骤 3：添加复选框类型内容控件
创建一个`StructuredDocumentTag`和`SdtType.Checkbox`表示复选框内容控件。指定`MarkupLevel.Inline`将其放置在文本中。

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## 步骤 4：保存文档
使用将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档保存为“WorkingWithSdt.CheckBoxTypeContentControl.docx”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### 使用 Aspose.Words for .NET 的复选框类型内容控制的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

就是这样！您已成功使用 Aspose.Words for .NET 在 Word 文档中创建了复选框类型内容控件。