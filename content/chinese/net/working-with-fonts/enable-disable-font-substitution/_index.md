---
title: 启用禁用字体替换
linktitle: 启用禁用字体替换
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中启用或禁用字体替换。确保您的文档在所有平台上看起来一致。
type: docs
weight: 10
url: /zh/net/working-with-fonts/enable-disable-font-substitution/
---
## 介绍

您是否遇到过这样的情况：在另一台计算机上查看时，Word 文档中精心选择的字体被替换了？很烦人，对吧？这是由于字体替换而发生的，字体替换是系统用可用字体替换丢失的字体的过程。但不用担心！使用 Aspose.Words for .NET，您可以轻松管理和控制字体替换。在本教程中，我们将引导您完成在 Word 文档中启用或禁用字体替换的步骤，确保您的文档始终符合您的要求。

## 先决条件

在开始这些步骤之前，请确保您已准备好所需的一切：

-  Aspose.Words for .NET：下载最新版本[这里](https://releases.aspose.com/words/net/).
- Visual Studio：任何支持 .NET 的版本。
- C# 的基本知识：这将帮助您理解编码示例。

## 导入命名空间

首先，确保已在项目中导入必要的命名空间。将这些添加到 C# 文件的顶部：

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

现在，让我们将这个过程分解为简单、易于管理的步骤。

## 步骤 1：设置你的项目

首先，在 Visual Studio 中设置一个新项目并添加对 Aspose.Words for .NET 库的引用。如果您还没有，请从[Aspose 网站](https://releases.aspose.com/words/net/).

## 步骤 2：加载文档

接下来，加载要处理的文档。操作方法如下：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

代替`"YOUR DOCUMENT DIRECTORY"`替换为文档目录的实际路径。此代码将文档加载到内存中，以便您可以对其进行操作。

## 步骤 3：配置字体设置

现在，让我们创建一个`FontSettings`对象来管理字体替换设置：

```csharp
FontSettings fontSettings = new FontSettings();
```

## 步骤 4：设置默认字体替换

将默认字体替换设置为您选择的字体。如果原始字体不可用，则将使用此字体：

```csharp
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

在这个例子中，我们使用 Arial 作为默认字体。

## 步骤 5：禁用字体信息替换

要禁用字体信息替换（阻止系统用可用字体替换丢失的字体），请使用以下代码：

```csharp
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
```

## 步骤 6：将字体设置应用于文档

现在，将这些设置应用到您的文档：

```csharp
doc.FontSettings = fontSettings;
```

## 步骤 7：保存文档

最后，保存修改后的文档。您可以将其保存为任何您喜欢的格式。在本教程中，我们将其保存为 PDF：

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```

## 结论

就这样！按照这些步骤，您可以使用 Aspose.Words for .NET 轻松控制 Word 文档中的字体替换。这样可以确保您的文档无论在何处查看，都能保持其预期的外观和感觉。

## 常见问题解答

### 我可以使用 Arial 以外的字体进行替代吗？

当然可以！您可以通过更改字体名称来指定系统上可用的任何字体`DefaultFontName`财产。

### 如果指定的默认字体不可用，会发生什么情况？

如果默认字体不可用，Aspose.Words 将使用系统回退机制来寻找合适的替代字体。

### 禁用字体替换后我可以再次启用它吗？

是的，你可以切换`Enabled`的財產`FontInfoSubstitution`返回`true`如果您想再次启用字体替换。

### 有没有办法检查哪些字体被替换了？

是的，Aspose.Words 提供了记录和跟踪字体替换的方法，让您可以看到哪些字体被替换了。

### 除了 DOCX 之外，我可以将此方法用于其他文档格式吗？

当然！Aspose.Words 支持多种格式，您可以将这些字体设置应用于任何支持的格式。