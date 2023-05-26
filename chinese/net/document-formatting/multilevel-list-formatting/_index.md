---
title: 多级列表格式
linktitle: 多级列表格式
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 创建多级列表和应用自定义格式。
type: docs
weight: 10
url: /zh/net/document-formatting/multilevel-list-formatting/
---

在本教程中，我们将向您展示如何使用 Aspose.Words for .NET 的多级列表格式化功能。按照以下步骤了解源代码并应用更改。

## 第 1 步：创建和配置文档

首先，创建一个新文档和一个关联的 DocumentBuilder 对象。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：格式化多级列表

我们现在将使用 DocumentBuilder 对象中可用的方法来应用多级列表格式。就是这样：

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## 第 3 步：保存文档

插入文本输入表单域后，使用`Save`方法。确保提供适当的文件路径：

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### 使用 Aspose.Words for .NET 的多级列表格式示例源代码

以下是 Aspose.Words for .NET 的多级列表格式化功能的完整源代码：


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ListFormat.ApplyNumberDefault();
	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.1");
	builder.Writeln("Item 2.2");
	
	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.2.1");
	builder.Writeln("Item 2.2.2");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 2.3");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 3");

	builder.ListFormat.RemoveNumbers();
	
	doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

使用此代码，您将能够创建一个多级列表并使用 Aspose.Words for .NET 将适当的格式应用到每个级别。