---
title: 启用禁用字体替换
linktitle: 启用禁用字体替换
second_title: Aspose.Words for .NET API 参考
description: 在本教程中，学习如何使用 Aspose.Words for .NET 在 Word 文档中启用或禁用字体替换。
type: docs
weight: 10
url: /zh/net/working-with-fonts/enable-disable-font-substitution/
---
在本教程中，我们将向您介绍如何在使用 .NET 的 Aspose.Words 库呈现 Word 文档时启用或禁用字体替换。启用或禁用字体替换允许您控制丢失的字体是否自动替换为默认字体。我们将带您一步一步地帮助您理解和实现您的 .NET 项目中的代码。

## 先决条件
在开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库
- 要使用或不使用字体替换呈现的 Word 文档

## 第一步：定义文档目录
首先，您需要将目录路径设置为您的 Word 文档所在的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：上传文档并配置字体设置
接下来，我们将加载您要呈现的 Word 文档并创建`FontSettings`类来处理字体设置。我们将通过在中指定字体名称来设置默认字体覆盖`DefaultFontName`并禁用字体信息覆盖`Enabled`设置`false`.

```csharp
//装入文档
Document doc = new Document(dataDir + "Rendering.docx");

//配置字体设置
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

//将字体设置应用于文档
doc.FontSettings = fontSettings;
```

## 第 3 步：保存呈现的文档
最后，我们将保存呈现的文档，这将遵循定义的字体覆盖设置。

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### 使用 Aspose.Words for .NET 启用禁用字体替换的示例源代码 

```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## 结论
在本教程中，我们了解了如何在使用 Aspose.Words for .NET 呈现 Word 文档时启用或禁用字体替换。通过控制字体替换，您可以影响在呈现的文档中处理缺失字体的方式。不要犹豫，使用此功能自定义 Word 文档中的字体管理。