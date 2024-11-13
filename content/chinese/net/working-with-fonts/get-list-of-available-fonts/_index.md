---
title: 获取可用字体列表
linktitle: 获取可用字体列表
second_title: Aspose.Words 文档处理 API
description: 在本详细的分步教程中了解如何使用 Aspose.Words for .NET 获取可用字体列表。提高您的字体管理技能。
type: docs
weight: 10
url: /zh/net/working-with-fonts/get-list-of-available-fonts/
---
## 介绍

您是否曾经发现自己难以管理 Word 文档中的字体？如果您是 .NET 开发人员，Aspose.Words for .NET 可以帮您！这个功能强大的库不仅可以帮助您以编程方式创建和操作 Word 文档，还提供广泛的字体管理功能。在本指南中，我们将引导您逐步了解如何使用 Aspose.Words for .NET 获取可用字体列表。我们将把它分解为易于理解的步骤，以确保您能够轻松跟上。那么，让我们开始吧，让字体管理变得轻而易举！

## 先决条件

在开始之前，您需要准备一些东西：

-  Aspose.Words for .NET：确保已安装 Aspose.Words for .NET 库。您可以从以下位置下载[这里](https://releases.aspose.com/words/net/).
- Visual Studio：本示例使用Visual Studio作为开发环境。
- .NET Framework：确保您的机器上安装了 .NET Framework。
- 文档目录：存储文档的目录路径。

## 导入命名空间

首先，将必要的命名空间导入到您的项目中：

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

## 步骤 1：初始化字体设置

第一步是初始化字体设置。这将允许您管理文档的字体来源。

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

- FontSettings：该类用于指定字体替换和字体源的设置。
- fontSources：我们从当前字体设置中创建现有字体源的列表。

## 第 2 步：定义文档目录

接下来，指定文档目录的路径。这是 Aspose.Words 将搜索字体的地方。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir：此字符串变量保存字体所在目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`与实际路径。

## 步骤 3：添加自定义字体文件夹

现在，添加一个新的文件夹源来指示 Aspose.Words 在该文件夹中搜索字体。

```csharp
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
```

- FolderFontSource：该类表示文件夹字体源。第二个参数（`true`)表示是否在子文件夹中递归搜索字体。

## 步骤 4：更新字体源

将自定义字体文件夹添加到现有字体源列表中并更新字体设置。

```csharp
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

- fontSources.Add(folderFontSource)：将自定义字体文件夹添加到现有字体源。
- updatedFontSources：将字体源列表转换为数组。

## 步骤 5：检索并显示字体

最后，检索可用的字体并显示其详细信息。

```csharp
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
    Console.WriteLine("Version  : " + fontInfo.Version);
    Console.WriteLine("FilePath : " + fontInfo.FilePath);
}
```

- GetAvailableFonts()：从更新列表中的第一个字体源检索可用字体列表。
-  fontInfo：一个实例`PhysicalFontInfo`包含每种字体的详细信息。

## 结论

恭喜！您已成功使用 Aspose.Words for .NET 检索可用字体列表。本教程将引导您完成每个步骤，从初始化字体设置到显示字体详细信息。有了这些知识，您现在可以轻松管理 Word 文档中的字体。请记住，Aspose.Words for .NET 是一个功能强大的工具，可以显著增强您的文档处理能力。因此，请继续探索更多功能，让您的开发过程更加高效。

## 常见问题解答

### 我可以将 Aspose.Words for .NET 与其他 .NET 框架一起使用吗？
是的，Aspose.Words for .NET 与各种 .NET 框架兼容，包括 .NET Core 和 .NET 5+。

### 如何安装 Aspose.Words for .NET？
您可以通过 Visual Studio 中的 NuGet 包管理器搜索“Aspose.Words”来安装它。

### 可以添加多个自定义字体文件夹吗？
是的，您可以通过创建多个来添加多个自定义字体文件夹`FolderFontSource`实例并将它们添加到字体源列表中。

### 我可以从特定字体源检索字体详细信息吗？
是的，您可以通过在`updatedFontSources`大批。

### Aspose.Words for .NET 支持字体替换吗？
是的，它支持字体替换，以确保即使原始字体不可用，文本也能正确呈现。