---
title: 获取可用字体列表
linktitle: 获取可用字体列表
second_title: Aspose.Words 文档处理 API
description: 在本教程中，了解如何获取 Aspose.Words for .NET 中可用的字体列表。
type: docs
weight: 10
url: /zh/net/working-with-fonts/get-list-of-available-fonts/
---
在本教程中，我们将解释如何获取 Aspose.Words for .NET 中可用的字体列表。可用字体列表可让您了解可以在文档中使用哪些字体。我们将逐步指导您理解并实现 .NET 项目中的代码。

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

## 第 2 步：配置字体源
接下来，我们将创建一个实例`FontSettings`并使用以下命令获取现有字体源`GetFontsSources()`方法。我们还将通过指定包含字体的文件夹来添加新的字体源。

```csharp
//配置字体源
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

//添加新的字体源
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## 步骤 3：获取可用字体列表
现在我们将使用以下命令浏览可用字体`GetAvailableFonts()`第一个更新的字体源上的方法。

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
//将包含我们的字体的自定义文件夹添加到现有字体源列表中。
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
在本教程中，我们了解了如何获取 Aspose.Words for .NET 中可用的字体列表。这可以让您知道可以在文档中使用哪些字体。请随意使用此功能来选择适合您需要的字体。

### 常见问题解答

#### 问：如何检索 Aspose.Words 中可用的字体列表？

答：要检索 Aspose.Words 中可用的字体列表，您可以使用`FontsProvider`类和`GetAvailableFonts`方法。此方法将返回系统上安装的所有字体的列表。

#### 问：我可以在 Aspose.Words 中按特定条件过滤可用字体列表吗？

答：是的，您可以使用特定条件过滤 Aspose.Words 中可用的字体列表。例如，您可以按系列、样式或语言过滤字体。

#### 问：如何在 Word 文档中使用可用字体列表？

答：要使用 Word 文档中可用的字体列表，您可以浏览该列表并使用 Word 文档中的方法和属性来选择合适的字体。`FontSettings` Aspose.Words 中的类。