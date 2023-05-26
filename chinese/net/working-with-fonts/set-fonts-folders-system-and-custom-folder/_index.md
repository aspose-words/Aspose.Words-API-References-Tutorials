---
title: 设置字体文件夹系统和自定义文件夹
linktitle: 设置字体文件夹系统和自定义文件夹
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 呈现文档时设置系统和自定义字体文件夹的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

在本教程中，我们将逐步指导您在使用 Aspose.Words for .NET 渲染文档时设置系统字体文件夹和自定义文件夹。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，以帮助您了解并在您自己的项目中实现此功能。在本教程结束时，您将知道如何指定多个字体文件夹，包括系统文件夹和自定义文件夹，以在使用 Aspose.Words for .NET 呈现文档时使用。

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

## 第 3 步：设置系统和自定义字体文件夹
现在您可以使用设置系统字体文件夹和自定义文件夹`FontSettings`类和`SetFontsSources()`方法。首先，您需要使用检索依赖于环境的字体源列表`GetFontsSources()`并将其存储在列表中。然后你可以创建一个新的实例`FolderFontSource`指定包含您的字体的自定义文件夹的路径。将此实例添加到现有字体源列表中。最后，使用`SetFontsSources()`使用新列表更新字体源。

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## 第 4 步：应用字体设置
接下来，您需要使用`FontSettings`的财产`Document`班级。

```csharp
doc.FontSettings = fontSettings;
```

## 第 5 步：保存呈现的文档
最后，您可以将呈现的文档保存到文件中

  使用`Save()`的方法`Document`班级。请务必指定正确的路径和文件名。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### 使用 Aspose.Words for .NET 设置字体文件夹系统和自定义文件夹的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	//检索默认搜索的环境相关字体源数组。
	//例如，这将包含 Windows 机器上的“Windows\Fonts\”源。
	//我们将这个数组添加到一个新的列表中，以便更容易地添加或删除字体条目。
	List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
	//添加一个新的文件夹源，它将指示 Aspose.Words 在以下文件夹中搜索字体。
	FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
	//将包含我们字体的自定义文件夹添加到现有字体源列表中。
	fontSources.Add(folderFontSource);
	FontSourceBase[] updatedFontSources = fontSources.ToArray();
	fontSettings.SetFontsSources(updatedFontSources);
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## 结论
在本教程中，我们学习了如何在使用 Aspose.Words for .NET 呈现文档时设置系统字体文件夹和自定义文件夹。按照此分步指南，您可以轻松指定多个字体文件夹，包括系统文件夹和自定义文件夹，以在呈现文档时使用。 Aspose.Words 提供了强大而灵活的 API 来处理文档中的字体。有了这些知识，您就可以控制和自定义在根据您的特定需求呈现文档时使用的字体源。