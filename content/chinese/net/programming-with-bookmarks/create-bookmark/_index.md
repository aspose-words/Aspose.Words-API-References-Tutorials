---
title: 在Word文档中创建书签
linktitle: 在Word文档中创建书签
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建书签并在 PDF 中指定书签预览级别。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/create-bookmark/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的创建书签功能。此功能允许您在文档中创建书签并在输出 PDF 文件中指定书签预览级别。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第 1 步：创建文档和生成器

在创建书签之前，我们需要使用以下命令创建一个文档和一个文档生成器`Document`和`DocumentBuilder`对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：创建主书签

我们使用`StartBookmark`启动主书签的方法和`EndBookmark`方法来结束它。在两者之间，我们可以添加文本和其他书签：

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

//在此处添加更多书签或文本。

builder. EndBookmark("My Bookmark");
```

## 第 3 步：创建嵌套书签

我们还可以在主书签内创建嵌套书签。我们用同样的`StartBookmark`和`EndBookmark`创建和结束嵌套书签的方法：

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## 步骤 4：在输出 PDF 文件中指定书签预览级别

我们使用`PdfSaveOptions`对象来指定输出 PDF 文件中的书签预览级别。我们使用`BookmarksOutlineLevels`财产

  添加主书签和嵌套书签及其各自的级别：

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### 使用 Aspose.Words for .NET 创建书签的示例源代码

以下是演示使用 Aspose.Words for .NET 创建书签的完整示例源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 的创建书签功能。我们按照分步指南在文档中创建书签并在输出 PDF 文件中指定书签预览级别。

### 常见问题解答

#### 问：使用 Aspose.Words for .NET 中的“创建书签”功能有哪些先决条件？

答：要使用Aspose.Words for .NET中的“创建书签”功能，您必须具备C#语言的基础知识。您还需要一个安装了 Aspose.Words 库的 .NET 开发环境。

#### 问：如何在 Aspose.Words for .NET 中创建文档？

答：要在 Aspose.Words for .NET 中创建文档，您可以使用`Document`班级。这是示例代码：

```csharp
Document doc = new Document();
```

#### 问：如何使用 Aspose.Words for .NET 在文档中创建主书签？

答：要使用 Aspose.Words for .NET 在文档中创建主书签，您可以使用`StartBookmark`方法启动书签，在里面添加文本或其他书签，然后使用` EndBookmark`结束它。这是示例代码：

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### 问：如何使用 Aspose.Words for .NET 在主书签内创建嵌套书签？

答：要使用 Aspose.Words for .NET 在主书签内创建嵌套书签，您可以使用相同的`StartBookmark`和`EndBookmark`开始和结束嵌套书签的方法。这是示例代码：

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### 问：如何使用 Aspose.Words for .NET 在输出 PDF 中指定书签预览级别？

答：要使用 Aspose.Words for .NET 在输出 PDF 中指定书签预览级别，您可以使用`PdfSaveOptions`类和`BookmarksOutlineLevels`财产。您可以添加主书签和嵌套书签及其各自的级别。这是示例代码：

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### 问：使用 Aspose.Words for .NET 创建书签后如何保存文档？

答：要在使用 Aspose.Words for .NET 创建书签后保存文档，您可以使用`Save`的方法`Document`指定目标文件路径的对象。这是示例代码：

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### 问：如何使用 Aspose.Words for .NET 在输出 PDF 中指定书签预览级别？

答：要使用 Aspose.Words for .NET 在输出 PDF 中指定书签预览级别，您可以使用`PdfSaveOptions`类和`BookmarksOutlineLevels`财产。您可以添加主书签和嵌套书签及其各自的级别。这是示例代码：

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### 问：如何使用 Aspose.Words for .NET 在主书签内创建嵌套书签？

答：要使用 Aspose.Words for .NET 在主书签内创建嵌套书签，您可以使用相同的`StartBookmark`和`EndBookmark`开始和结束嵌套书签的方法。调用时请务必指定父书签作为参数`StartBookmark`方法。这是示例代码：

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### 问：如何使用 Aspose.Words for .NET 在书签内添加文本？

答：要使用 Aspose.Words for .NET 在书签内添加文本，您可以使用`Write`的方法`DocumentBuilder`指定要添加的文本的对象。这是示例代码：

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### 问：如何使用 Aspose.Words for .NET 在文档中创建主书签？

答：要使用 Aspose.Words for .NET 在文档中创建主书签，您可以使用`StartBookmark`启动书签的方法和`EndBookmark`方法来结束它。这是示例代码：

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```