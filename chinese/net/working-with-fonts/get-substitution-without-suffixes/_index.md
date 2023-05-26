---
title: 获取没有后缀的替换
linktitle: 获取没有后缀的替换
second_title: Aspose.Words for .NET API 参考
description: 在本教程中，了解如何使用 Aspose.Words for .NET 在 Word 文档中获取无后缀覆盖。
type: docs
weight: 10
url: /zh/net/working-with-fonts/get-substitution-without-suffixes/
---

在本教程中，我们将向您展示如何使用 .NET 的 Aspose.Words 库在 Word 文档中获取不带后缀的覆盖。不带后缀的替换用于解决显示或打印文档时的字体替换问题。我们将带您一步一步地帮助您理解和实现您的 .NET 项目中的代码。

## 先决条件
在开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库

## 第一步：定义文档目录
首先，您需要将目录路径设置为您的 Word 文档所在的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载文档并配置不带后缀的替换
接下来，我们将使用`Document`使用类和配置无后缀替换`DocumentSubstitutionWarnings`班级。我们还将通过指定包含字体的文件夹来添加字体源。

```csharp
//加载文档并配置不带后缀的替换
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## 第 3 步：保存文档
最后，我们将保存应用了无后缀覆盖的文档。

```csharp
//保存文件
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### 使用 Aspose.Words for .NET 获取无后缀替换的示例源代码 
```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## 结论
在本教程中，我们看到了如何使用 Aspose.Words for .NET 在 Word 文档中获取没有后缀的覆盖。不带后缀的替换对于解决字体替换问题很有用。随意使用此功能来改进文档的显示和打印。
