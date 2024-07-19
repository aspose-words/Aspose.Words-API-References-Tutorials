---
title: 删除线
linktitle: 删除线
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 分步指南应用删除线文本样式。
type: docs
weight: 10
url: /zh/net/working-with-markdown/strikethrough/
---


在此示例中，我们将引导您了解如何使用 Aspose.Words for .NET 应用删除线文本样式。删除线文本用于指示文本已被删除或不再有效。

## 步骤 1：使用文档生成器

首先，我们将使用文档生成器向文档添加内容。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 步骤 2：应用删除线文本样式

我们将通过设置`StrikeThrough`的财产`Font`反对`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## 步骤 3：添加删除线文本

我们现在可以使用文档生成器的`Writeln`方法。

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### 使用 Aspose.Words for .NET 的删除线文本示例源代码

```csharp
//使用文档生成器向文档添加内容。
DocumentBuilder builder = new DocumentBuilder();

//给文本添加删除线。
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 应用删除线文本样式。

### 常见问题解答

#### 问：如何在 Aspose.Words 中添加删除线文本？

答：要在 Aspose.Words 中添加删除线文本，您可以使用`Font.StrikeThrough`的财产`Run`对象。您可以将此属性设置为`true`为特定文本添加删除线文本。例如，您可以使用`run.Font.StrikeThrough=true`将删除线文本添加到`Run`目的。

#### 问： 是否可以为同一段中的几段文字添加删除线文字？

答：是的，您可以使用多个`Run`对象。您可以创建多个`Run`对象并设置`Font.StrikeThrough`财产`true`为每个对象添加删除线文本到所需的文本部分。然后，您可以使用`Paragraph.AppendChild(run)`方法。

#### 问：我可以为 Aspose.Words 中表格或单元格中的文本添加删除线文本吗？

答：是的，您可以在 Aspose.Words 中的表格或单元格中添加删除线文本。您可以使用适当的方法跳转到所需的单元格或段落，然后使用`Font.StrikeThrough`的财产`Run`或者`Paragraph`目的。