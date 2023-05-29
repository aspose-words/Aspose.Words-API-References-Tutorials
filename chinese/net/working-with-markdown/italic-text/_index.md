---
title: 斜体文字
linktitle: 斜体文字
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 分步指南将文本设置为斜体。
type: docs
weight: 10
url: /zh/net/working-with-markdown/italic-text/
---

在本例中，我们将带您了解如何使用 Aspose.Words for .NET 的斜体文本功能。斜体文本用于强调文档的某些部分。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：将文本设为斜体

我们可以通过设置字体的斜体`Italic`财产给`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### 使用 Aspose.Words for .NET 的斜体文本示例源代码


```csharp
//使用文档生成器向文档添加内容。
DocumentBuilder builder = new DocumentBuilder();

//使文本斜体。
builder.Font.Italic = true;
builder.Writeln("This text will be Italic");
```

恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 的斜体文本功能。

