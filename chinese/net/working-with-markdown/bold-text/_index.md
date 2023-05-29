---
title: 加粗字体
linktitle: 加粗字体
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 分步指南将文本加粗。
type: docs
weight: 10
url: /zh/net/working-with-markdown/bold-text/
---

在本例中，我们将告诉您如何使用 Aspose.Words for .NET 将文本加粗。粗体文本使其更显眼并更加突出。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：粗体文本

我们可以通过设置文档生成器的`Font.Bold`财产给`true`.

```csharp
builder.Font.Bold = true;
```

## 第 3 步：向文档添加内容

现在我们可以使用文档生成器方法向文档添加内容，例如`Writeln`添加一行文本。

```csharp
builder.Writeln("This text will be bold");
```

## 使用 Aspose.Words for .NET 的粗体文本示例源代码


```csharp
//使用文档生成器向文档添加内容。
DocumentBuilder builder = new DocumentBuilder();

//将文本设为粗体。
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

恭喜！您现在已经学习了如何使用 Aspose.Words for .NET 将文本加粗。


