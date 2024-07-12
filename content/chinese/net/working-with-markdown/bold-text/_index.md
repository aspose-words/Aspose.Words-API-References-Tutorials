---
title: 加粗字体
linktitle: 加粗字体
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 分步指南加粗文本。
type: docs
weight: 10
url: /zh/net/working-with-markdown/bold-text/
---

在此示例中，我们将告诉您如何使用 Aspose.Words for .NET 加粗文本。加粗文本使其更加明显，更加突出。

## 步骤 1：使用文档生成器

首先，我们将使用文档生成器向文档添加内容。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：粗体文本

我们可以通过设置文档生成器的`Font.Bold`财产`true`.

```csharp
builder.Font.Bold = true;
```

## 步骤 3：向文档添加内容

现在我们可以使用文档构建器方法向文档添加内容，例如`Writeln`，添加一行文本。

```csharp
builder.Writeln("This text will be bold");
```

## 使用 Aspose.Words for .NET 实现粗体文本的示例源代码


```csharp
//使用文档生成器向文档添加内容。
DocumentBuilder builder = new DocumentBuilder();

//使文本变为粗体。
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

恭喜！您现在已经学会了如何使用 Aspose.Words for .NET 加粗文本。


### 常见问题解答

#### 问：如何在 Aspose.Words 中使文本变粗体？

答：要在 Aspose.Words 中将文本加粗，您可以使用`Font.Bold`的财产`Run`对象。您可以将此属性设置为`true`加粗特定文本。例如，您可以使用`run.Font.Bold=true`加粗文本`Run`目的。

#### 问：是否可以将同一段文字加粗？

答：是的，您可以使用多个`Run`对象。您可以创建多个`Run`对象并设置`Font.Bold`财产`true`为每个对象添加所需的文本部分。然后，您可以使用`Paragraph.AppendChild(run)`方法。

#### 问：我可以加粗 Aspose.Words 中表格或单元格中的文本吗？

答：是的，您可以在 Aspose.Words 中将表格或单元格中的文本加粗。您可以使用适当的方法导航到所需的单元格或段落，然后使用`Font.Bold`的财产`Run`或者`Paragraph`目的。