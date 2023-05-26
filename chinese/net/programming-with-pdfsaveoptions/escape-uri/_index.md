---
title: 转义 URI
linktitle: 转义 URI
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 转义 Uri 的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/escape-uri/
---

本文提供了有关如何使用 Aspose.Words for .NET 的 Uri 转义功能的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何在文档中插入带有转义 Uri 的超链接。

在开始之前，请确保您已经在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第一步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建一个文档和一个 DocumentBuilder

接下来，我们需要创建一个新的`Document`对象和一个`DocumentBuilder`构建文档的对象。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：插入带有转义 Uri 的超链接

使用`InsertHyperlink`的方法`DocumentBuilder`对象将超链接插入到文档中。 Uri 必须使用`Uri.EscapeUriString`避免格式错误的功能。

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
```

## 第 4 步：将文档另存为 PDF

最后，我们可以使用`Save`的方法`Document`目的。指定输出文件名。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

就这样 ！您已使用 Aspose.Words for .NET 在文档中成功插入带有转义 Uri 的超链接。

### 使用 Aspose.Words for .NET 转义 Uri 的示例源代码


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
