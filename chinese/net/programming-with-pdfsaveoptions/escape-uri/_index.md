---
title: PDF 文档中的转义 URI
linktitle: PDF 文档中的转义 URI
second_title: Aspose.Words for .NET API 参考
description: 分步指南如何使用 Aspose.Words for .NET 在 PDF 文档中转义 URI。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/escape-uri/
---

本文提供了有关如何使用 Aspose.Words for .NET 转义 PDF 文档中的 URI 的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何在文档中插入带有转义 Uri 的超链接。

在开始之前，请确保您已在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第1步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建文档和 DocumentBuilder

接下来，我们需要创建一个新的`Document`对象和一个`DocumentBuilder`对象来构建文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：插入带有转义 Uri 的超链接

使用`InsertHyperlink`的方法`DocumentBuilder`对象将超链接插入到文档中。 Uri 必须使用转义`Uri.EscapeUriString`函数以避免格式错误。

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
```

## 步骤 4：将文档另存为 PDF

最后，我们可以使用以下命令将文档另存为 PDF：`Save`的方法`Document`目的。指定输出文件名。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

就这样 ！您已使用 Aspose.Words for .NET 在文档中成功插入带有转义 Uri 的超链接。

### 使用 Aspose.Words for .NET 进行 Uri 转义的示例源代码


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", false);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", false);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## 结论

在本教程中，我们介绍了如何使用 Aspose.Words for .NET 在 PDF 文档中转义 URI。通过转义 URI，您可以避免格式错误并确保超链接在 PDF 文档中得到正确解释和显示。按照概述的步骤将带有转义 URI 的超链接插入到 PDF 文档中。一定要逃走。

### 经常问的问题

#### 问：PDF 文档中的转义 URI 是什么？为什么它很重要？
答：PDF文档中的转义URI是指将URL中的特殊字符转换为转义序列以避免格式错误的方法。这很重要，因为 URL 中的特殊字符可能会破坏 URL 的结构并导致误解或不正确的呈现。通过转义特殊字符，我们保证 URL 被正确解释并显示在 PDF 文档中。

#### 问：如何使用 Aspose.Words for .NET 转义 PDF 文档中的 URI？
答：要使用 Aspose.Words for .NET 转义 PDF 文档中的 URI，请按照下列步骤操作：

通过替换设置文档所在的目录路径`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

创建一个新实例`Document`类和一个`DocumentBuilder`对象来构建文档。

使用`InsertHyperlink`的方法`DocumentBuilder`对象将超链接插入到文档中。确保使用转义 URI`Uri.EscapeUriString`函数以避免格式错误。

使用`Save`的方法`Document`对象通过指定输出文件的名称将文档保存为 PDF 格式。

#### 问：在 PDF 文档中转义 URI 有什么好处？
答：在 PDF 文档中转义 URI 的好处是：

防止格式错误：URI 转义有助于防止 URL 中的特殊字符引起的格式错误，确保 URL 被正确解释并显示在 PDF 文档中。

与 PDF 阅读器的兼容性：转义 URI 通常受到 PDF 阅读器的良好支持，确保更好的兼容性和一致的用户体验。

#### 问：URI 中哪些特殊字符应该转义？
答：URI 中必须转义的特殊字符有：空格、<、>、"、#、%、{、}、|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.