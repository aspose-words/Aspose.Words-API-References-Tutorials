---
title: 将字体导出为 Base 64
linktitle: 将字体导出为 Base 64
second_title: Aspose.Words 文档处理 API
description: 在此详细教程中了解如何使用 Aspose.Words for .NET 将字体导出为 Base64。确保字体嵌入并正确显示在 HTML 文件中。
type: docs
weight: 10
url: /zh/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---
## 介绍

在以编程方式操作 Word 文档时，Aspose.Words for .NET 是一个强大的工具。它的一个巧妙功能是将字体导出为 HTML 文件中的 Base64，确保字体在不同的浏览器和系统中正确嵌入和显示。在本教程中，我们将深入介绍如何实现这一点。准备好让您的 Word 文档字体适合网络了吗？让我们开始吧！

## 先决条件

在我们开始编码之前，让我们确保您拥有所需的一切：

-  Aspose.Words for .NET 库：您可以从[Aspose 版本](https://releases.aspose.com/words/net/)页。
- .NET 开发环境：任何 IDE（如 Visual Studio）都可以完美运行。
- C# 基础知识：您不需要成为专业人士，但基本的了解会有所帮助。

## 导入命名空间

要使用 Aspose.Words for .NET，您需要在 C# 代码中导入必要的命名空间。这样所有类和方法都可以使用。

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 步骤 1：设置你的项目

首先，让我们设置您的项目并安装 Aspose.Words 库。

### 1.1 创建新项目

打开 Visual Studio 并创建一个新的控制台应用程序项目。将其命名为“ExportFontsBase64”等有意义的名称。

### 1.2 安装 Aspose.Words

您可以通过 NuGet 包管理器安装 Aspose.Words for .NET：

1. 在解决方案资源管理器中右键单击您的项目。
2. 选择“管理 NuGet 包”。
3. 搜索“Aspose.Words”并安装。

或者，您可以在程序包管理器控制台中运行以下命令：

```sh
Install-Package Aspose.Words
```

## 第 2 步：加载 Word 文档

现在您的项目已经设置好了，让我们加载您想要从中导出字体的 Word 文档。

### 2.1 定义文档目录

首先，定义您的 Word 文档所在的目录：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

### 2.2 加载文档

接下来，使用`Document`班级：

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

确保“Rendering.docx”位于您指定的目录中。

## 步骤 3：配置 HTML 保存选项

要将字体导出为 Base64，我们需要配置`HtmlSaveOptions`.


创建一个实例`HtmlSaveOptions`并设置`ExportFontsAsBase64`财产`true`：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

## 步骤 4：将文档保存为 HTML

最后，让我们保存配置了选项的文档。


使用`Save`方法`Document`保存文档的类：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

此行将把您的文档保存为 HTML 文件，并将字体导出为 Base64，确保它们嵌入在 HTML 中。

## 结论

恭喜！您已成功使用 Aspose.Words for .NET 将字体从 Word 文档导出为 Base64。这可确保您的字体在不同平台上得到保留并正确显示。无论您是准备用于 Web 显示的文档还是仅仅确保兼容性，此功能都非常有用。

## 常见问题解答

### 什么是 Base64 编码？
Base64 是一种将二进制数据（如字体）编码为文本格式的方法。这确保了与 HTML 等基于文本的格式的兼容性。

### 为什么应该在 HTML 中对字体使用 Base64？
使用 Base64 可确保字体直接嵌入 HTML 中，避免缺少字体文件的问题并确保显示的一致性。

### 我可以将此方法用于图像等其他资源吗？
当然！Aspose.Words for .NET 允许您将各种资源（包括图像）以 Base64 格式嵌入到 HTML 文件中。

### 如果我的文档有多种字体怎么办？
没问题！Aspose.Words for .NET 会将文档中使用的所有字体以 Base64 格式嵌入到生成的 HTML 文件中。

### Aspose.Words for .NET 可以免费使用吗？
 Aspose.Words for .NET 是一个商业库。不过，你可以从[Aspose 版本](https://releases.aspose.com/)页。
