---
title: 设置字体文件夹多个文件夹
linktitle: 设置字体文件夹多个文件夹
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 呈现文档时设置多个字体文件夹的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

在本教程中，我们将逐步指导您在使用 Aspose.Words for .NET 渲染文档时设置多个字体文件夹。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，以帮助您了解并在您自己的项目中实现此功能。在本教程结束时，您将了解如何指定多个字体文件夹以在使用 Aspose.Words for .NET 呈现文档时使用。

## 第一步：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑后的渲染文档的位置。用适当的路径替换“您的文档目录”。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载要呈现的文档
然后您可以加载文档以使用`Document`班级。请务必指定正确的文档路径。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 第 3 步：设置字体文件夹
现在您可以使用设置多个字体文件夹`FontSettings`类和`SetFontsFolders()`方法。您可以指定要在数组中使用的字体文件夹的路径。在此示例中，我们指定了两个字体文件夹：“C:\MyFonts\" 和 "D:\Misc\Fonts\”。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## 第 4 步：应用字体设置
接下来，您需要使用`FontSettings`的财产`Document`班级。

```csharp
doc.FontSettings = fontSettings;
```

## 第 5 步：保存呈现的文档
最后，您可以使用`Save()`的方法`Document`班级。请务必指定正确的路径和文件名。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### 使用 Aspose.Words for .NET 设置字体文件夹多个文件夹的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	//请注意，此设置将覆盖默认搜索的任何默认字体源。现在只会搜索这些文件夹
	//渲染或嵌入字体时的字体。要在保留系统字体源的同时添加额外的字体源，请同时使用 FontSettings.GetFontSources 和
	//改为使用 FontSettings.SetFontSources。
	fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## 结论
在本教程中，我们学习了如何在使用 Aspose.Words for .NET 渲染文档时设置多个字体文件夹。按照此分步指南，您可以轻松指定多个字体文件夹以在呈现文档时使用。 Aspose.Words 提供了强大而灵活的 API 来处理文档中的字体。有了这些知识，您就可以控制和自定义在根据您的特定需求呈现文档时使用的字体源。