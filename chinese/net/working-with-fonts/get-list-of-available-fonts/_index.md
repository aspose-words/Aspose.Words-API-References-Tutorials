---
title: 获取可用字体列表
linktitle: 获取可用字体列表
second_title: Aspose.Words for .NET API 参考
description: 在本教程中，学习如何获取 Aspose.Words for .NET 中可用的字体列表。
type: docs
weight: 10
url: /zh/net/working-with-fonts/get-list-of-available-fonts/
---
在本教程中，我们将解释如何获取 Aspose.Words for .NET 中可用的字体列表。可用字体列表让您知道可以在文档中使用哪些字体。我们将带您一步一步地帮助您理解和实现您的 .NET 项目中的代码。

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

## 第二步：配置字体源
接下来，我们将创建一个实例`FontSettings`并使用`GetFontsSources()`方法。我们还将通过指定包含字体的文件夹来添加新的字体源。

```csharp
//配置字体源
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

//添加新的字体源
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## 第 3 步：获取可用字体列表
现在我们将使用`GetAvailableFonts()`第一个更新的字体源上的方法。

```csharp
//获取可用字体列表
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### 使用 Aspose.Words for .NET 获取可用字体列表的示例源代码 

```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
//添加一个新的文件夹源，它将指示 Aspose.Words 在以下文件夹中搜索字体。
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
//将包含我们字体的自定义文件夹添加到现有字体源列表中。
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## 结论
在本教程中，我们了解了如何获取 Aspose.Words for .NET 中可用的字体列表。这让您知道可以在文档中使用哪些字体。随意使用此功能来选择适合您需要的字体。