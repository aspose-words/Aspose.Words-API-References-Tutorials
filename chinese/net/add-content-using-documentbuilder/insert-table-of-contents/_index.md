---
title: 在 Word 文档中插入目录
linktitle: 在 Word 文档中插入目录
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中插入目录。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/insert-table-of-contents/
---
在这个综合教程中，您将学习如何使用 Aspose.Words for .NET 将目录插入到 Word 文档中。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够生成具有适当标题和页码的目录。

## 先决条件
在我们开始之前，请确保您满足以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建新文档和 DocumentBuilder
首先，使用 Document 类创建一个新文档并初始化 DocumentBuilder 对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入目录
接下来，使用 DocumentBuilder 类的 InsertTableOfContents 方法插入目录。在方法中指定所需的格式选项：

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## 第三步：添加文档内容
插入目录后，添加实际的文档内容。使用 StyleIdentifier 设置适当的标题样式：

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## 第 4 步：更新目录
新插入的目录最初是空的。要填充它，请更新文档中的字段：

```csharp
doc.UpdateFields();
```

## 第 5 步：保存文档
插入目录并更新字段后，使用 Document 类的 Save 方法将文档保存到文件中：

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### 使用 Aspose.Words for .NET 插入目录的示例源代码
以下是使用 Aspose.Words for .NET 插入目录的完整源代码：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

//使用 Document 对象初始化 DocumentBuilder
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//插入目录a
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

//从第二页开始实际文档内容。
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


//新插入的目录最初是空的。
//需要通过更新文档中的字段来填充它。
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## 结论

恭喜！您已成功学习如何使用 Aspose.Words for .NET 将目录插入到 Word 文档中。通过遵循此分步指南并利用提供的源代码，您现在可以为文档生成包含适当标题和页码的目录。

### 在Word文档中插入目录的常见问题解答

#### 问：我可以自定义目录的外观吗？

答：是的，您可以通过修改在中指定的格式选项来自定义目录的外观。`InsertTableOfContents`方法。这些参数允许您控制页码、缩进和其他样式。

#### 问：如果我想在目录中包含特定标题级别该怎么办？

答：您可以通过调整范围内的值来指定要包含在目录中的所需标题级别。`InsertTableOfContents`方法。例如，使用`"\\o \"1-3\""`将包括标题级别 1 至 3。

#### 问：如果我更改文档内容，可以自动更新目录吗？

答：是的，您可以通过调用自动更新目录`UpdateFields`文档上的方法。这将确保对文档内容所做的任何更改（例如添加或删除标题）都会反映在目录中。

#### 问：如何对目录中的标题级别设置不同的样式？

答：您可以通过为每个标题级别使用不同的段落样式来设置不同的标题级别样式。通过分配不同的`StyleIdentifier`值对`ParagraphFormat`的`DocumentBuilder`，您可以为每个标题级别创建不同的样式。

#### 问：是否可以为目录中的标题添加其他格式？

答：是的，您可以向目录中的标题添加其他格式，例如字体样式、颜色或其他属性。通过调整`Font`的属性`DocumentBuilder`，您可以将自定义格式应用于标题。