---
title: 组合框内容控件
linktitle: 组合框内容控件
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建组合框内容控件。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/combo-box-content-control/
---

本教程介绍如何使用 Aspose.Words for .NET 在 Word 文档中创建组合框内容控件。组合框内容控件允许用户从下拉列表中选择一个项目。

## 先决条件
要学习本教程，您需要具备以下条件：

- 安装了 Aspose.Words for .NET 库。
- C# 的基本知识和使用 Word 文档。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用要保存文档的目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建文档和 StructuredDocumentTag
创建一个新的实例`Document`类和一个`StructuredDocumentTag`表示组合框内容控件。指定`SdtType.ComboBox`作为类型和`MarkupLevel.Block`作为创建块级组合框的标记级别。

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## 第 3 步：将项目添加到组合框
使用`ListItems`的财产`StructuredDocumentTag`.每个项目都由一个`SdtListItem`对象，它带有一个显示文本和一个值。在此示例中，我们将三个项目添加到组合框。

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## 第 4 步：将 StructuredDocumentTag 附加到文档
使用`AppendChild`文档第一部分正文的方法。

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## 第 5 步：保存文档
使用 将文档保存到指定目录`Save`方法。提供具有适当文件扩展名的所需文件名。在本例中，我们将文档保存为“WorkingWithSdt.ComboBoxContentControl.docx”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### 使用 Aspose.Words for .NET 的组合框内容控件示例源代码 

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

就是这样！您已经使用 Aspose.Words for .NET 在您的 Word 文档中成功创建了一个组合框内容控件。