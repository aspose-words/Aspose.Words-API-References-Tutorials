---
title: 加粗字体
linktitle: 加粗字体
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 分步指南将文本加粗。
type: docs
weight: 10
url: /zh/net/working-with-markdown/bold-text/
---

在此示例中，我们将告诉您如何使用 Aspose.Words for .NET 将文本加粗。粗体文本使其更加明显并更加突出。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：粗体文本

我们可以通过设置文档生成器的`Font.Bold`财产给`true`.

```csharp
builder.Font.Bold = true;
```

## 步骤 3：向文档添加内容

现在我们可以使用文档构建器方法向文档添加内容，例如`Writeln`，这会添加一行文本。

```csharp
builder.Writeln("This text will be bold");
```

## 使用 Aspose.Words for .NET 的粗体文本示例源代码


```csharp
//使用文档生成器将内容添加到文档中。
DocumentBuilder builder = new DocumentBuilder();

//将文本设为粗体。
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 将文本加粗。


### 常见问题解答

#### 问：如何在 Aspose.Words 中将文本设为粗体？

答：要在 Aspose.Words 中将文本设为粗体，您可以使用`Font.Bold`的财产`Run`目的。您可以将此属性设置为`true`将特定文本加粗。例如，您可以使用`run.Font.Bold=true`将里面的文本加粗`Run`目的。

#### 问：是否可以将同一段落中的多段文字加粗？

答：是的，您可以使用多个将单个段落中的多段文本加粗`Run`对象。您可以创建多个`Run`对象并设置`Font.Bold`财产给`true`对于每个对象，将所需的文本部分加粗。然后您可以使用以下命令将它们添加到段落中`Paragraph.AppendChild(run)`方法。

#### 问：我可以将 Aspose.Words 中表格或单元格中的文本加粗吗？

答：是的，您可以在 Aspose.Words 中将表格或单元格中的文本加粗。您可以使用适当的方法导航到所需的单元格或段落，然后使用`Font.Bold`的财产`Run`或者`Paragraph`目的。