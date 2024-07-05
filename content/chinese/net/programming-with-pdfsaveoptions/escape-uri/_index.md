---
title: PDF 文档中的转义 URI
linktitle: PDF 文档中的转义 URI
second_title: Aspose.Words 文档处理 API
description: 逐步指南如何使用 Aspose.Words for .NET 转义 PDF 文档中的 URI。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/escape-uri/
---

本文提供了如何使用 Aspose.Words for .NET 在 PDF 文档中转义 URI 的分步指南。我们将详细解释代码的每个部分。在本教程结束时，您将能够了解如何在文档中插入带有转义 Uri 的超链接。

开始之前，请确保您已在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到该库和安装说明。

## 步骤1：定义文档目录

首先，您需要定义文档所在目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：创建文档和 DocumentBuilder

接下来，我们需要创建一个新的`Document`对象和一个`DocumentBuilder`对象来构建文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：插入带有转义 Uri 的超链接

使用`InsertHyperlink`方法`DocumentBuilder`对象以将超链接插入文档。必须使用`Uri.EscapeUriString`函数以避免格式错误。

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test”），false）；
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test”），
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test”），false）；
```

## 步骤 4：将文档另存为 PDF

最后，我们可以使用`Save`方法`Document`对象。指定输出文件名。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

就这样！您已成功使用 Aspose.Words for .NET 在文档中插入带有转义 Uri 的超链接。

### 使用 Aspose.Words for .NET 进行 Uri 转义的示例源代码


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test",错误);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test",错误);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## 结论

在本教程中，我们介绍了如何使用 Aspose.Words for .NET 转义 PDF 文档中的 URI。通过转义 URI，您可以避免格式错误并确保超链接在 PDF 文档中得到正确解释和显示。按照概述的步骤将带有转义 URI 的超链接插入 PDF 文档。务必转义。

### 经常问的问题

#### 问：PDF 文档中的转义 URI 是什么？为什么它很重要？
答：PDF 文档中的转义 URI 是指将 URL 中的特殊字符转换为转义序列以避免格式错误的方法。这很重要，因为 URL 中的特殊字符会破坏 URL 的结构并导致误解或不正确的渲染。通过转义特殊字符，我们可以保证 URL 被正确解释并显示在 PDF 文档中。

#### 问：如何使用 Aspose.Words for .NET 转义 PDF 文档中的 URI？
答：要使用 Aspose.Words for .NET 转义 PDF 文档中的 URI，请按照以下步骤操作：

通过替换来设置文档所在的目录路径`"YOUR DOCUMENT DIRECTORY"`与您的文档目录的实际路径。

创建一个新的实例`Document`类和一个`DocumentBuilder`对象来构建文档。

使用`InsertHyperlink`方法`DocumentBuilder`对象将超链接插入到文档中。请务必使用`Uri.EscapeUriString`函数以避免格式错误。

使用`Save`方法`Document`对象通过指定输出文件的名称将文档保存为 PDF 格式。

#### 问：在 PDF 文档中转义 URI 有什么好处？
答：PDF 文档中进行 URI 转义的好处有：

防止格式错误：URI 转义有助于防止由 URL 中的特殊字符导致的格式错误，确保 URL 被正确解释并显示在 PDF 文档中。

与 PDF 阅读器的兼容性：转义的 URI 通常受到 PDF 阅读器的良好支持，从而确保更好的兼容性和一致的用户体验。

#### 问：URI 中应该转义哪些特殊字符？
答：URI 中必须转义的特殊字符有：空格、<、>、"、#、%、{、}，|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.