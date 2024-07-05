---
title: 组合框内容控件
linktitle: 组合框内容控件
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建组合框内容控件。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/combo-box-content-control/
---

本教程介绍如何使用 Aspose.Words for .NET 在 Word 文档中创建组合框内容控件。组合框内容控件允许用户从下拉列表中选择一个项目。

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
创建一个新的实例`Document`类和一个`StructuredDocumentTag`表示组合框内容控件。指定`SdtType.ComboBox`作为类型和`MarkupLevel.Block`作为标记级别来创建块级组合框。

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## 步骤 3：将项目添加到组合框
使用`ListItems`的财产`StructuredDocumentTag` 每个项目由一个`SdtListItem`对象，它接受显示文本和值。在此示例中，我们向组合框添加了三个项目。

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## 步骤 4：将 StructuredDocumentTag 附加到文档
使用将组合框内容控件附加到文档主体`AppendChild`文档第一部分主体的方法。

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## 步骤 5：保存文档
使用将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档保存为“WorkingWithSdt.ComboBoxContentControl.docx”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### 使用 Aspose.Words for .NET 的组合框内容控制示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

就是这样！您已成功使用 Aspose.Words for .NET 在 Word 文档中创建了组合框内容控件。