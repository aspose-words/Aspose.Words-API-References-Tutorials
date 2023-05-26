---
title: 移动到页眉页脚
linktitle: 移动到页眉页脚
second_title: Aspose.Words for .NET API 参考
description: 通过此分步指南，了解如何使用 Aspose.Words for .NET 在 Word 文档中导航和修改页眉和页脚。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/move-to-headers-footers/
---

在这个例子中，我们将探索 Aspose.Words for .NET 的 Move To Headers Footers 特性。 Aspose.Words 是一个强大的文档操作库，允许开发人员以编程方式创建、修改和转换 Word 文档。移动到页眉/页脚功能使我们能够导航到文档中的不同页眉和页脚并向它们添加内容。

让我们逐步浏览源代码，了解如何使用 Aspose.Words for .NET 的移动到页眉/页脚功能。



## 第 1 步：初始化文档和文档生成器

首先，初始化 Document 和 DocumentBuilder 对象：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：配置页眉和页脚

指定文档的页眉/页脚设置。在此示例中，我们将首页和奇数/偶数页的页眉和页脚设置为不同：

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## 第 3 步：为不同的页面创建标题

移动到每个标题类型并向它们添加内容。在此示例中，我们为第一页、偶数页和所有其他页面创建标题：

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## 第 4 步：在文档中创建页面
将内容添加到文档以创建多个页面。例如：

```csharp
//在文档中创建两个页面。
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## 第 5 步：保存文档

将修改后的文档保存到所需位置：

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

确保指定适当的文件路径和格式（例如，DOCX）。

### 使用 Aspose.Words for .NET 移动到页眉/页脚的示例源代码

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//指定我们希望首页、偶数页和奇数页的页眉和页脚不同。
	builder.PageSetup.DifferentFirstPageHeaderFooter = true;
	builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

	//创建标题。
	builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
	builder.Write("Header for the first page");
	builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
	builder.Write("Header for even pages");
	builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
	builder.Write("Header for all other pages");

	//在文档中创建两个页面。
	builder.MoveToSection(0);
	builder.Writeln("Page1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("Page2");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");

```
