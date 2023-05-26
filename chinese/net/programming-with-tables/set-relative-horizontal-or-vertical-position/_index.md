---
title: 设置相对水平或垂直位置
linktitle: 设置相对水平或垂直位置
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 设置表格在 Word 文档中的相对水平或垂直位置。
type: docs
weight: 10
url: /zh/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

在本教程中，我们将学习如何使用 Aspose.Words for .NET 设置 Word 文档中表格的相对水平或垂直位置。我们将按照逐步指南来理解代码并实现此功能。在本教程结束时，您将能够在 Word 文档中设置表格的相对水平或垂直位置。

## 第 1 步：项目设置
1. 启动 Visual Studio 并创建一个新的 C# 项目。
2. 添加对 Aspose.Words for .NET 库的引用。

## 第 2 步：装入文档
要开始使用该文档，请执行以下步骤：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//装入文档
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

请务必将“您的文档目录”替换为文档目录的实际路径并提供正确的文件名。

## 第三步：设置表格的相对位置
接下来，我们将设置表格的相对水平或垂直位置。使用以下代码：

```csharp
//检索表
Table table = doc.FirstSection.Body.Tables[0];

//工作台相对水平位置的定义
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

//定义表格的相对垂直位置
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

这里我们使用文档从第一节的正文中检索第一个表。接下来，我们设置表格的相对水平位置`HorizontalAnchor`属性使用`RelativeHorizontalPosition.Column`价值。同样，我们设置表格的相对垂直位置`VerticalAnchor`属性使用`RelativeVerticalPosition.Page`价值。

## 第 4 步：保存修改后的文档
最后，我们需要保存修改后的文档，并定义表格的相对位置。使用以下代码：

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
在本教程中，我们学习了如何使用 Aspose.Words for .NET 设置 Word 文档中表格的相对水平或垂直位置。通过遵循此分步指南并实施提供的 C# 代码，您可以将此相对位置应用于 Word 文档中的表格。