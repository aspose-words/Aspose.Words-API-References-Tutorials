---
title: 关联
linktitle: 关联
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 插入链接。分步指南。
type: docs
weight: 10
url: /zh/net/working-with-markdown/link/
---

在这个例子中，我们将带您了解如何使用 Aspose.Words for .NET 的链接功能。链接用于创建对网站或其他文档的可点击引用。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：插入链接

我们可以使用`Insertlink`文档生成器的方法。我们需要指定链接文本，这里是“Aspose”，以及目标 URL。

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com", false);
```

### 与 Aspose.Words for .NET 链接的示例源代码


```csharp
//使用文档生成器向文档添加内容。
DocumentBuilder builder = new DocumentBuilder();

//插入链接。
builder.Insertlink("Aspose", "https://www.aspose.com", false);
```
恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 的链接功能。

