---
title: 自动链接
linktitle: 自动链接
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 一步一步指南插入自动链接。
type: docs
weight: 10
url: /zh/net/working-with-markdown/autolink/
---

在本例中，我们将解释如何使用 Aspose.Words for .NET 的“自动链接”功能。此功能允许您自动将超链接插入文档。

## 步骤 1：使用文档生成器

首先，我们将使用文档生成器向文档添加内容。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 步骤 2：插入超链接

我们可以使用`InsertHyperlink`文档生成器的方法。我们指定 URL 和要显示的链接文本。

```csharp
builder.InsertHyperlink("https://www.aspose.com”， “https://www.aspose.com”， false);
```

## 步骤 3：插入电子邮件地址作为链接

我们还可以使用“mailto:”前缀将电子邮件地址作为链接插入。这样用户点击链接即可打开其默认电子邮件客户端。

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## 步骤 4：保存文档

最后，我们可以以所需的格式保存文档。

### 使用 Aspose.Words for .NET 进行自动链接的示例源代码


```csharp
//使用文档生成器向文档添加内容。
DocumentBuilder builder = new DocumentBuilder();

//插入超链接。
builder.InsertHyperlink("https://www.aspose.com”， “https://www.aspose.com”， false);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 的“自动链接”功能。


### 常见问题解答

#### 问：如何在 Aspose.Words 中创建到 URL 地址的自动链接？

答：要在 Aspose.Words 中创建指向 URL 地址的自动链接，您可以使用`<a>`标记`href`包含 URL 地址的属性。例如，您可以使用`<a href="https://www.aspose.com">https://www.aspose.com</a>`自动链接到“https://www.aspose.com”。

#### 问：是否可以自定义 Aspose.Words 中自动链接的显示文本？

答：是的，您可以在 Aspose.Words 中自定义自动链接的显示文本。除了使用 URL 地址作为显示文本外，您还可以使用任何其他文本，只需替换`<a>`标签。例如，您可以使用`<a href="https://www.aspose.com">Click here</a>`将文本“单击此处”显示为自动链接。

#### 问：如何在 Aspose.Words 中向自动链接添加附加属性？

答：要在 Aspose.Words 中向自动链接添加其他属性，您可以在`<a>`标签。例如，您可以使用`<a href="https://www.aspose.com" target="_blank">Link</a>`使用` attribute target="_blank"`.