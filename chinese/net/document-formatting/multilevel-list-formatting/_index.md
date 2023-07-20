---
title: Word 文档中的多级列表格式
linktitle: Word 文档中的多级列表格式
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 创建多级列表并在 Word 文档中应用自定义格式。
type: docs
weight: 10
url: /zh/net/document-formatting/multilevel-list-formatting/
---
在本教程中，我们将向您展示如何通过 Aspose.Words for .NET 使用 Word 文档功能中的多级列表格式。请按照以下步骤了解源代码并应用更改。

## 第 1 步：创建并配置文档

首先，创建一个新文档和关联的 DocumentBuilder 对象。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 2：格式化多级列表

现在，我们将使用 DocumentBuilder 对象中可用的方法应用多级列表格式。就是这样：

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

## 步骤 3：保存文档

插入文本输入表单字段后，使用以下命令将文档保存到所需位置`Save`方法。确保提供适当的文件路径：

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### 使用 Aspose.Words for .NET 进行多级列表格式化的示例源代码

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

通过此代码，您将能够创建多级列表，并使用 Aspose.Words for .NET 对每个级别应用正确的格式。


## 结论

在本教程中，我们探索了通过 Aspose.Words for .NET 在 Word 文档中利用多级列表格式化功能的过程。通过遵循概述的步骤，您可以创建组织良好的多个级别的列表，从而增强文档的结构和可读性。

### 常见问题解答

#### 问：什么是Word文档中的多级列表？

答：Word 文档中的多级列表是一个分层列表，允许您将项目组织为不同级别的子项目。它有助于以结构化的方式呈现信息，使读者更容易理解内容。

#### 问：我可以自定义多级列表的外观吗？

答：是的，您可以自定义 Word 文档中多级列表的外观。通过应用不同的样式（例如项目符号、数字或字母）以及调整缩进和间距，您可以创建一个具有视觉吸引力且组织有序的列表。

#### 问：Aspose.Words for .NET 支持其他列表格式选项吗？

答：是的，Aspose.Words for .NET 提供了一套全面的列表格式化功能。它支持各种列表类型，包括项目符号列表、编号列表和多级列表。您可以操纵列表的格式、添加或删除项目以及自定义其外观。

#### 问：我可以使用 Aspose.Words for .NET 处理其他文档元素吗？

答：是的，Aspose.Words for .NET 提供了处理各种文档元素（例如段落、表格、图像等）的广泛功能。它使您能够以编程方式创建、修改和转换 Word 文档，从而简化文档处理任务。