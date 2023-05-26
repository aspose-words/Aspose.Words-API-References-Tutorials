---
title: 字体设置默认实例
linktitle: 字体设置默认实例
second_title: Aspose.Words for .NET API 参考
description: 在本教程中，学习如何使用 Aspose.Words for .NET 在 Word 文档中配置默认字体设置。
type: docs
weight: 10
url: /zh/net/working-with-fonts/font-settings-default-instance/
---

在本教程中，我们将带您了解如何使用 .NET 的 Aspose.Words 库在 Word 文档中配置默认字体设置。默认字体设置允许您指定加载和呈现文档时使用的字体源。我们将带您一步一步地帮助您理解和实现您的 .NET 项目中的代码。

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

## 第 2 步：配置默认字体设置
接下来，我们将创建一个实例`FontSettings`使用`FontSettings.DefaultInstance`，然后我们将指定加载和呈现文档时使用的字体源。在此示例中，我们使用系统字体源和文件夹字体源。

```csharp
//配置默认字体设置
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## 第 3 步：上传带有字体设置的文档
现在我们将使用加载文档`LoadOptions`并指定要使用的字体设置。

```csharp
//使用字体设置加载文档
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### 使用 Aspose.Words for .NET 的字体设置默认实例的示例源代码 
```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## 结论
在本教程中，我们了解了如何使用 Aspose.Words for .NET 在 Word 文档中配置默认字体设置。通过指定加载和呈现文档时使用的字体源，您可以控制文档中字体的外观。随意使用此功能自定义项目中的字体设置。