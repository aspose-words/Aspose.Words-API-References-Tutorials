---
title: 设置字体文件夹
linktitle: 设置字体文件夹
second_title: Aspose.Words for .NET API 参考
description: 了解如何在 Aspose.Words for .NET 中设置字体目录并确保文档中使用的字体的可用性。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-fonts-folder/
---
在本教程中，我们将向您展示如何在 Aspose.Words for .NET 中设置字体目录。您将学习如何指定包含 Word 文档中使用的字体的目录。

## 先决条件
在开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库

## 第一步：定义文档目录
首先将目录路径设置为 Word 文档的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第二步：设置字体目录
创建一个实例`FontSettings`上课并使用`SetFontsFolder`方法来指定包含字体的目录。代替`"Fonts"`使用实际字体目录的名称。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## 第 3 步：加载带有字体设置的文档
使用`LoadOptions`类来指定字体设置`FontSettings`选项。然后使用`Document`使用这些选项加载文档的类。

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### 使用 Aspose.Words for .NET 设置字体文件夹的示例源代码 

```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## 结论
恭喜！您现在知道如何在 Aspose.Words for .NET 中设置字体目录了。您可以使用此功能来确保文档中使用的字体的可用性，并确保字体显示的一致性。
