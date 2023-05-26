---
title: 创建书签
linktitle: 创建书签
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在文档中创建书签并在 PDF 中指定书签预览级别。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/create-bookmark/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的创建书签功能。此功能允许您在文档中创建书签并在输出 PDF 文件中指定书签预览级别。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第 1 步：创建文档和生成器

在创建书签之前，我们需要使用`Document`和`DocumentBuilder`对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：创建主书签

我们使用`StartBookmark`启动主书签的方法和`EndBookmark`结束它的方法。在这两者之间，我们可以添加文本和其他书签：

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

//在此处添加更多书签或文本。

builder. EndBookmark("My Bookmark");
```

## 第 3 步：创建嵌套书签

我们还可以在主书签内创建嵌套书签。我们用的一样`StartBookmark`和`EndBookmark`创建和结束嵌套书签的方法：

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## 步骤 4：在输出 PDF 文件中指定书签预览级别

我们使用`PdfSaveOptions`对象指定输出 PDF 文件中的书签预览级别。我们使用`BookmarksOutlineLevels`财产

  添加具有各自级别的主书签和嵌套书签：

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

在本文中，我们探索了 C# 源代码以了解如何使用 Aspose.Words for .NET 的创建书签功能。我们已按照分步指南在文档中创建书签并在输出 PDF 文件中指定书签预览级别。