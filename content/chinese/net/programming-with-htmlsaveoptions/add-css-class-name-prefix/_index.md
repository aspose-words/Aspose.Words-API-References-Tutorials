---
title: 添加 Css 类名前缀
linktitle: 添加 Css 类名前缀
second_title: Aspose.Words 文档处理 API
description: 了解如何在使用 Aspose.Words for .NET 将 Word 文档保存为 HTML 时添加 CSS 类名前缀。其中包括分步指南、代码片段和常见问题解答。
type: docs
weight: 10
url: /zh/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---
## 介绍

欢迎！如果您正在深入了解 Aspose.Words for .NET 的世界，那么您将大饱眼福。今天，我们将探讨如何在使用 Aspose.Words for .NET 将 Word 文档保存为 HTML 时添加 CSS 类名前缀。当您想避免 HTML 文件中的类名冲突时，此功能非常方便。

## 先决条件

在开始之前，请确保您已准备好以下内容：

-  Aspose.Words for .NET：如果您尚未安装，[点击下载](https://releases.aspose.com/words/net/).
- 开发环境：Visual Studio 或任何其他 C# IDE。
-  Word 文档：我们将使用名为`Rendering.docx`将其放置在您的项目目录中。

## 导入命名空间

首先，确保已将必要的命名空间导入到 C# 项目中。在代码文件顶部添加以下内容：

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

现在，让我们深入了解分步指南！

## 步骤 1：设置你的项目

在我们开始添加 CSS 类名前缀之前，让我们先设置我们的项目。

### 步骤 1.1：创建新项目

启动 Visual Studio 并创建一个新的控制台应用程序项目。将其命名为类似以下名称的朗朗上口的名字：`AsposeCssPrefixExample`.

### 步骤1.2：添加Aspose.Words for .NET

如果您还没有，请通过 NuGet 将 Aspose.Words for .NET 添加到您的项目中。只需打开 NuGet 包管理器控制台并运行：

```bash
Install-Package Aspose.Words
```

太棒了！现在，我们可以开始编码了。

## 步骤 2：加载文档

我们需要做的第一件事是加载要转换为 HTML 的 Word 文档。

### 步骤 2.1：定义文档路径

设置文档目录的路径。为了便于本教程，我们假设您的文档位于名为`Documents`在您的项目目录中。

```csharp
string dataDir = @"C:\YourProject\Documents\";
```

### 步骤 2.2：加载文档

现在，让我们使用 Aspose.Words 加载文档：

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步骤 3：配置 HTML 保存选项

接下来，我们需要配置 HTML 保存选项以包含 CSS 类名前缀。

### 步骤 3.1：创建 HTML 保存选项

实例化`HtmlSaveOptions`对象并将 CSS 样式表类型设置为`External`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External
};
```

### 步骤 3.2：设置 CSS 类名前缀

现在，让我们设置`CssClassNamePrefix`属性。在本例中，我们将使用`"pfx_"`.

```csharp
saveOptions.CssClassNamePrefix = "pfx_";
```

## 步骤 4：将文档保存为 HTML

最后，让我们使用配置的选项将文档保存为 HTML 文件。


指定输出 HTML 文件路径并保存文档。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

## 步骤 5：验证输出

运行项目后，导航到您的`Documents`文件夹。您应该会找到一个名为`WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html` 在文本编辑器或浏览器中打开此文件，以验证 CSS 类是否具有前缀`pfx_`.

## 结论

就这样！按照这些步骤，您已成功使用 Aspose.Words for .NET 将 CSS 类名前缀添加到 HTML 输出中。这个简单但功能强大的功能可以帮助您在 HTML 文档中保持干净且无冲突的样式。

## 常见问题解答

### 我可以对每次保存操作使用不同的前缀吗？
是的，您可以在每次保存文档时通过更改`CssClassNamePrefix`财产。

### 此方法是否支持内联 CSS？
这`CssClassNamePrefix`属性适用于外部 CSS。对于内联 CSS，您需要采用不同的方法。

### 我如何包含其他 HTML 保存选项？
您可以配置各种属性`HtmlSaveOptions`自定义 HTML 输出。检查[文档](https://reference.aspose.com/words/net/)更多细节。

### 是否可以将 HTML 保存到流中？
当然可以！你可以将流对象传递给`Save`方法。

### 如果我遇到问题，如何获得支持？
您可以从[Aspose 论坛](https://forum.aspose.com/c/words/8).