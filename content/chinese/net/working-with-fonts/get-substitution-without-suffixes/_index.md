---
title: 获取不带后缀的替换
linktitle: 获取不带后缀的替换
second_title: Aspose.Words 文档处理 API
description: 了解如何在 Aspose.Words for .NET 中管理不带后缀的字体替换。请遵循我们的分步指南，确保您的文档每次都看起来完美。
type: docs
weight: 10
url: /zh/net/working-with-fonts/get-substitution-without-suffixes/
---

欢迎阅读这份有关使用 Aspose.Words for .NET 管理字体替换的综合指南。如果您曾经因文档中的字体无法正确显示而苦恼过，那么您来对地方了。本教程将引导您逐步完成有效处理无后缀的字体替换的过程。让我们开始吧！

## 先决条件

在深入学习本教程之前，请确保您具备以下条件：

- C# 基础知识：了解 C# 编程将使您更容易遵循和实现这些步骤。
-  Aspose.Words for .NET Library：从以下位置下载并安装该库：[下载链接](https://releases.aspose.com/words/net/).
- 开发环境：设置 Visual Studio 等开发环境来编写和运行代码。
- 示例文档：示例文档（例如，`Rendering.docx`）在本教程中使用。

## 导入命名空间

首先，我们需要导入必要的命名空间来访问 Aspose.Words 提供的类和方法。

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using Aspose.Words.WarningInfo;
using System.Collections.Generic;
```

## 第 1 步：定义文档目录

首先，指定文档所在的目录。这有助于找到您想要处理的文档。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：设置替换警告处理程序

接下来，我们需要设置一个警告处理程序，只要在文档处理过程中发生字体替换，它就会通知我们。这对于捕获和处理任何字体问题至关重要。

```csharp
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
Document doc = new Document(dataDir + "Rendering.docx");
doc.WarningCallback = substitutionWarningHandler;
```

## 第 3 步：添加自定义字体源

在此步骤中，我们将添加自定义字体源，以确保 Aspose.Words 可以找到并使用正确的字体。如果您在自定义目录中存储了特定字体，这尤其有用。

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());

FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

在此代码中：
- 我们检索当前的字体源并添加新的`FolderFontSource`指向我们的自定义字体目录（`C:\\MyFonts\\`）。
- 然后，我们使用这个新列表更新字体源。

## 步骤 4：保存文档

最后，应用字体替换设置后保存文档。对于本教程，我们将其另存为 PDF。

```csharp
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

## 第 5 步：创建警告处理程序类

要有效地处理警告，请创建一个实现以下功能的自定义类`IWarningCallback`界面。此类将捕获并记录任何字体替换警告。

```csharp
public class DocumentSubstitutionWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

在本课程中：
- 这`Warning`方法捕获与字体替换相关的警告。
- 这`FontWarnings`集合存储这些警告以供进一步检查或记录。

## 结论

您现在已经掌握了使用 Aspose.Words for .NET 处理无后缀的字体替换的过程。这些知识将确保您的文档保持其预期的外观，无论系统上可用的字体如何。不断尝试不同的设置和来源，以充分利用 Aspose.Words 的强大功能。

## 常见问题解答

### Q1：如何使用多个自定义目录中的字体？

您可以添加多个`FolderFontSource`实例到`fontSources`相应地列出并更新字体源。

### 问题 2：哪里可以下载 Aspose.Words for .NET 的免费试用版？

您可以从以下位置下载免费试用版：[Aspose免费试用页面](https://releases.aspose.com/).

###  Q3：我可以使用处理多种类型的警告吗？`IWarningCallback`?

是的`IWarningCallback`界面允许您处理各种类型的警告，而不仅仅是字体替换。

### Q4：我在哪里可以获得 Aspose.Words 的支持？

如需支持，请访问[Aspose.Words 支持论坛](https://forum.aspose.com/c/words/8).

### Q5: 可以购买临时许可证吗？

是的，您可以从以下机构获得临时许可证[临时许可证页面](https://purchase.aspose.com/temporary-license/).