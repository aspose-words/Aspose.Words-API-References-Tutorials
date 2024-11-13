---
title: 将文本输入表单字段导出为文本
linktitle: 将文本输入表单字段导出为文本
second_title: Aspose.Words 文档处理 API
description: 通过本全面的分步指南了解如何使用 Aspose.Words for .NET 将文本输入表单字段导出为纯文本。
type: docs
weight: 10
url: /zh/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---
## 介绍

那么，您正在深入了解 Aspose.Words for .NET 的世界吗？很棒的选择！如果您想了解如何将文本输入表单字段导出为文本，那么您来对地方了。无论您是刚开始还是正在提高技能，本指南都将引导您了解您需要了解的一切。让我们开始吧，好吗？

## 先决条件

在我们深入讨论细节之前，让我们确保您已做好顺利进行所需的一切准备：

-  Aspose.Words for .NET：从以下网址下载并安装最新版本[这里](https://releases.aspose.com/words/net/).
- IDE：Visual Studio 或任何 C# 开发环境。
- 基本 C# 知识：了解基本 C# 语法和面向对象编程概念。
- 文档：示例 Word 文档 (`Rendering.docx`) 带有文本输入表单字段。

## 导入命名空间

首先，你需要导入必要的命名空间。这些命名空间就像是让一切无缝运行的构建块。

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Saving;
```

好了，现在我们已经准备好了命名空间，让我们开始行动吧！

## 步骤 1：设置项目

在我们进入代码之前，让我们确保我们的项目设置正确。

## 创建项目

1. 打开 Visual Studio：首先打开 Visual Studio 或您首选的 C# 开发环境。
2. 创建新项目：导航至`File > New > Project`。 选择`Console App (.NET Core)`或任何其他相关项目类型。
3. 命名您的项目：为您的项目起一个有意义的名字，例如`AsposeWordsExportExample`.

## 添加 Aspose.Words

1. 管理 NuGet 包：在解决方案资源管理器中右键单击你的项目，然后选择`Manage NuGet Packages`.
2. 搜索 Aspose.Words：在 NuGet 包管理器中，搜索`Aspose.Words`.
3. 安装 Aspose.Words：点击`Install`将 Aspose.Words 库添加到您的项目。

## 第 2 步：加载 Word 文档

现在我们的项目已经设置好了，让我们加载包含文本输入表单字段的 Word 文档。

1. 指定文档目录：定义存储文档的目录的路径。
2. 加载文档：使用`Document`类来加载你的Word文档。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步骤 3：准备导出目录

在导出之前，让我们确保导出目录已准备好。这是我们的 HTML 文件和图像将保存的地方。

1. 定义导出目录：指定导出文件的保存路径。
2. 检查并清理目录：确保目录存在并且为空。

```csharp
string imagesDir = Path.Combine(dataDir, "Images");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);
```

## 步骤 4：配置保存选项

奇迹就在这里发生。我们需要设置保存选项，以将文本输入表单字段导出为纯文本。

1. 创建保存选项：初始化一个新的`HtmlSaveOptions`目的。
2. 设置导出文本选项：配置`ExportTextInputFormFieldAsText`财产`true`.
3. 设置图像文件夹：定义保存图像的文件夹。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true,
    ImagesFolder = imagesDir
};
```

## 步骤 5：将文档保存为 HTML

最后，让我们使用配置的保存选项将 Word 文档保存为 HTML 文件。

1. 定义输出路径：指定 HTML 文件的保存路径。
2. 保存文档：使用`Save`方法`Document`类来导出文档。

```csharp
doc.Save(dataDir + "ExportedDocument.html", saveOptions);
```

## 结论

就这样！您已成功使用 Aspose.Words for .NET 将文本输入表单字段导出为纯文本。本指南应该为您提供了完成此任务的清晰、循序渐进的方法。请记住，熟能生巧，因此请继续尝试不同的选项和设置，看看您还可以使用 Aspose.Words 做什么。

## 常见问题解答

### 我可以使用相同方法导出其他类型的表单字段吗？

是的，您可以通过配置不同的属性来导出其他类型的表单字段`HtmlSaveOptions`班级。

### 如果我的文档中有图像怎么办？

图像将保存在指定的图像文件夹中。确保设置`ImagesFolder`财产在`HtmlSaveOptions`.

### 我需要 Aspose.Words 的许可证吗？

是的，您可以免费试用[这里](https://releases.aspose.com/)或购买许可证[这里](https://purchase.aspose.com/buy).

### 我可以自定义导出的 HTML 吗？

当然！Aspose.Words 提供了各种选项来自定义 HTML 输出。请参阅[文档](https://reference.aspose.com/words/net/)了解更多详情。

### Aspose.Words 与 .NET Core 兼容吗？

是的，Aspose.Words 与 .NET Core、.NET Framework 和其他 .NET 平台兼容。
