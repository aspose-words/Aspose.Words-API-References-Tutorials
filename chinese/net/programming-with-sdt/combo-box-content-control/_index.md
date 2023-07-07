---
title: 组合框内容控件
linktitle: 组合框内容控件
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建组合框内容控件。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/combo-box-content-control/
---

本教程介绍如何使用 Aspose.Words for .NET 在 Word 文档中创建组合框内容控件。组合框内容控件允许用户从下拉列表中选择项目。

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
创建一个新实例`Document`类和一个`StructuredDocumentTag`代表组合框内容控件。指定`SdtType.ComboBox`作为类型和`MarkupLevel.Block`作为标记级别来创建块级组合框。

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## 第 3 步：将项目添加到组合框
使用以下命令将项目添加到组合框`ListItems`的财产`StructuredDocumentTag`。每个项目都由一个表示`SdtListItem`对象，它接受显示文本和值。在此示例中，我们将三个项目添加到组合框中。

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## 步骤 4：将 StructuredDocumentTag 附加到文档
使用以下命令将组合框内容控件附加到文档正文`AppendChild`文档第一部分主体的方法。

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## 第 5 步：保存文档
使用以下命令将文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档另存为“WorkingWithSdt.ComboBoxContentControl.docx”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### 使用 Aspose.Words for .NET 的组合框内容控件的示例源代码 

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

就是这样！您已使用 Aspose.Words for .NET 在 Word 文档中成功创建了组合框内容控件。