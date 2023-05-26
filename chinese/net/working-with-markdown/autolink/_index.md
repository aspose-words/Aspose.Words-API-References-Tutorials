---
title: 自动链接
linktitle: 自动链接
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 分步指南插入自动链接。
type: docs
weight: 10
url: /zh/net/working-with-markdown/autolink/
---

在本例中，我们将解释如何使用 Aspose.Words for .NET 的“自动链接”功能。此功能允许您自动将超链接插入到文档中。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：插入超链接

我们可以使用`InsertHyperlink`文档生成器的方法。我们指定要为链接显示的 URL 和文本。

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
```

## 第 3 步：插入电子邮件地址作为链接

我们还可以使用“mailto:”前缀插入电子邮件地址作为链接。这将允许用户单击链接以打开他们的默认电子邮件客户端。

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## 第 4 步：保存文档

最后，我们可以将文档保存为所需的格式。

### 使用 Aspose.Words for .NET 的自动链接示例源代码


```csharp
	//使用文档生成器向文档添加内容。
	DocumentBuilder builder = new DocumentBuilder();

	//插入超链接。
	builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
	builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
            
```


恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 的“自动链接”功能。

