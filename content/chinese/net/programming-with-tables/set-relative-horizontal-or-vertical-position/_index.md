---
title: 设置相对水平或垂直位置
linktitle: 设置相对水平或垂直位置
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 设置 Word 文档中表格的相对水平或垂直位置。
type: docs
weight: 10
url: /zh/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 设置 Word 文档中表格的相对水平或垂直位置。我们将按照分步指南来理解代码并实现此功能。在本教程结束时，您将能够在 Word 文档中设置表格的相对水平或垂直位置。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：加载文档
要启动文档的文字处理，请按照下列步骤操作：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

请务必将“您的文档目录”替换为文档目录的实际路径，并提供正确的文件名。

## 第三步：设置表格的相对位置
接下来，我们将设置表格的相对水平或垂直位置。使用以下代码：

```csharp
//检索表
Table table = doc.FirstSection.Body.Tables[0];

//定义工作台的相对水平位置
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

//定义表格的相对垂直位置
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

这里我们使用文档从第一部分的正文中检索第一个表。接下来，我们使用以下命令设置表格的相对水平位置`HorizontalAnchor`属性使用`RelativeHorizontalPosition.Column`价值。类似地，我们设置表格的相对垂直位置`VerticalAnchor`属性使用`RelativeVerticalPosition.Page`价值。

## 第四步：保存修改后的文档
最后，我们需要保存修改后的文档并定义表格的相对位置。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

请务必为输出文档指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 设置相对水平或垂直位置的示例源代码 

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 设置 Word 文档中表格的相对水平或垂直位置。通过遵循此分步指南并实现提供的 C# 代码，您可以将此相对位置应用到 Word 文档中的表格。