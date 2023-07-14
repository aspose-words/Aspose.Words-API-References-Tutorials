---
title: 段落格式
linktitle: 段落格式
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将自定义格式应用于段落。
type: docs
weight: 10
url: /zh/net/document-formatting/paragraph-formatting/
---

在本教程中，我们将引导您了解如何使用 Aspose.Words for .NET 的段落格式功能。请按照以下步骤了解源代码并应用更改。

## 第 1 步：创建并配置文档

首先，创建一个新文档和关联的 DocumentBuilder 对象。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：设置段落格式

现在，我们将使用 DocumentBuilder 对象的 ParagraphFormat 对象中可用的属性将格式应用于段落。就是这样：

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.Alignment = ParagraphAlignment.Center;
paragraphFormat. LeftIndent = 50;
paragraphFormat. RightIndent = 50;
paragraphFormat. SpaceAfter = 25;
```

## 步骤 3：保存文档

插入文本输入表单字段后，使用以下命令将文档保存到所需位置`Save`方法。确保提供适当的文件路径：

```csharp
builder.Writeln(
	"I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
builder.Writeln(
	"I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");

doc.Save(dataDir + "DocumentFormatting.ParagraphFormatting.docx");
```

### 使用 Aspose.Words for .NET 进行段落格式设置的示例源代码

以下是 Aspose.Words for .NET 段落格式设置功能的完整源代码：


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.Alignment = ParagraphAlignment.Center;
	paragraphFormat.LeftIndent = 50;
	paragraphFormat.RightIndent = 50;
	paragraphFormat.SpaceAfter = 25;

	builder.Writeln(
		"I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
	builder.Writeln(
		"I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");

	doc.Save(dataDir + "DocumentFormatting.ParagraphFormatting.docx");
	
```

通过此代码，您将能够使用 Aspose.Words for .NET 对段落应用不同的格式。

