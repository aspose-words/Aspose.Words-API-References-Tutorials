---
title: 自动链接
linktitle: 自动链接
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 分步指南插入自动链接。
type: docs
weight: 10
url: /zh/net/working-with-markdown/autolink/
---

在此示例中，我们将解释如何使用 Aspose.Words for .NET 的“自动链接”功能。此功能允许您自动将超链接插入到文档中。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 步骤 2：插入超链接

我们可以使用以下命令插入超链接`InsertHyperlink`文档生成器的方法。我们指定 URL 和要为链接显示的文本。

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
```

## 第 3 步：插入电子邮件地址作为链接

我们还可以使用“mailto:”前缀插入电子邮件地址作为链接。这将允许用户单击链接来打开他们的默认电子邮件客户端。

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## 步骤 4：保存文档

最后，我们可以将文档保存为所需的格式。

### 使用 Aspose.Words for .NET 的自动链接示例源代码


```csharp
//使用文档生成器将内容添加到文档中。
DocumentBuilder builder = new DocumentBuilder();

//插入超链接。
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 的“自动链接”功能。


### 常见问题解答

#### 问：如何在 Aspose.Words 中创建指向 URL 地址的自动链接？

答：要在 Aspose.Words 中创建指向 URL 地址的自动链接，您可以使用`<a>`标签与`href`包含 URL 地址的属性。例如，您可以使用`<a href="https://www.aspose.com">https://www.aspose.com</a>`自动链接到“https://www.aspose.com”。

#### 问：是否可以在 Aspose.Words 中自定义自动链接的显示文本？

答：是的，您可以在 Aspose.Words 中自定义自动链接的显示文本。您可以通过替换 URL 地址之间的内容来使用任何其他文本，而不是使用 URL 地址作为显示文本。`<a>`标签。例如，您可以使用`<a href="https://www.aspose.com">Click here</a>`将文本“单击此处”显示为自动链接。

#### 问：如何向 Aspose.Words 中的自动链接添加其他属性？

答：要向 Aspose.Words 中的自动链接添加附加属性，您可以在`<a>`标签。例如，您可以使用`<a href="https://www.aspose.com" target="_blank">Link</a>`使用以下命令在新窗口或选项卡中打开链接` attribute target="_blank"`.