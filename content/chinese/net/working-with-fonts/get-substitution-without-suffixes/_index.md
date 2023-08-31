---
title: 获取不带后缀的替换
linktitle: 获取不带后缀的替换
second_title: Aspose.Words 文档处理 API
description: 在本教程中，了解如何使用 Aspose.Words for .NET 在 Word 文档中获取无后缀覆盖。
type: docs
weight: 10
url: /zh/net/working-with-fonts/get-substitution-without-suffixes/
---

在本教程中，我们将向您展示如何使用 .NET 的 Aspose.Words 库在 Word 文档中获取不带后缀的覆盖。无后缀替换用于解决显示或打印文档时的字体替换问题。我们将逐步指导您理解并实现 .NET 项目中的代码。

## 先决条件
开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库

## 第1步：定义文档目录
首先，您需要将目录路径设置为 Word 文档的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第2步：加载文档并配置不带后缀的替换
接下来，我们将使用以下命令加载文档`Document`类并使用以下命令配置无后缀替换`DocumentSubstitutionWarnings`班级。我们还将通过指定包含字体的文件夹来添加字体源。

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

## 步骤 3：保存文档
最后，我们将保存应用无后缀覆盖的文档。

```csharp
//保存文档
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### 使用 Aspose.Words for .NET 获取无后缀的替换的示例源代码 
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
在本教程中，我们了解了如何使用 Aspose.Words for .NET 在 Word 文档中获取不带后缀的覆盖。不带后缀的替换对于解决字体替换问题很有用。请随意使用此功能来改进文档的显示和打印。

### 常见问题解答

#### 问：为什么 Aspose.Words 在字体替换中添加后缀？

答：Aspose.Words 在字体替换中添加后缀，以避免原始字体和替换字体之间的冲突。这有助于确保转换和操作文档时的最大兼容性。

#### 问：如何在 Aspose.Words 中检索没有后缀的字体替换？

答：要在 Aspose.Words 中检索不带后缀的字体替换，您可以使用`FontSubstitutionSettings`类和`RemoveSuffixes`财产。将此属性设置为`true`将获得不添加后缀的字体替换。

#### 问：是否可以在 Aspose.Words 中禁用为字体替换添加后缀？

答：不，无法在 Aspose.Words 中禁用为字体替换添加后缀。默认添加后缀以确保文档兼容性和一致性。

#### 问：如何在 Aspose.Words 中过滤掉字体替换中不需要的后缀？

答：要过滤掉 Aspose.Words 中字体替换中不需要的后缀，可以使用字符串处理技术，例如使用`Replace`或者`Substring`删除您不想包含的特定后缀的方法。