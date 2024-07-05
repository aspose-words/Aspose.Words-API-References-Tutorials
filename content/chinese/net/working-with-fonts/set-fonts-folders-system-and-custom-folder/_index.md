---
title: 设置字体文件夹系统和自定义文件夹
linktitle: 设置字体文件夹系统和自定义文件夹
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 呈现文档时设置系统和自定义字体文件夹的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

在本教程中，我们将引导您逐步完成使用 Aspose.Words for .NET 渲染文档时设置系统字体文件夹和自定义文件夹的过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，以帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何指定多个字体文件夹，包括系统文件夹和自定义文件夹，以便在使用 Aspose.Words for .NET 渲染文档时使用。

## 步骤1：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑后的渲染文档的位置。将“YOUR DOCUMENTS DIRECTORY”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载要渲染的文档
然后你可以使用`Document`类。请确保指定正确的文档路径。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步骤 3：设置系统和自定义字体文件夹
现在，您可以使用`FontSettings`类和`SetFontsSources()`方法。首先，您需要使用以下方法检索依赖于环境的字体源列表`GetFontsSources()`并将其存储在列表中。然后你可以创建一个新的实例`FolderFontSource`指定包含字体的自定义文件夹的路径。将此实例添加到现有字体源列表中。最后，使用`SetFontsSources()`使用新列表更新字体源。

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## 步骤 4：应用字体设置
接下来，您需要使用`FontSettings`的财产`Document`班级。

```csharp
doc.FontSettings = fontSettings;
```

## 步骤 5：保存渲染的文档
最后，您可以通过以下方式将渲染的文档保存到文件中：

  使用`Save()`方法`Document`类。请确保指定正确的路径和文件名。

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
//我们将这个数组添加到一个新的列表中，以便更轻松地添加或删除字体条目。
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
在本教程中，我们学习了如何使用 Aspose.Words for .NET 渲染文档时设置系统字体文件夹和自定义文件夹。按照本分步指南，您可以轻松指定多个字体文件夹，包括系统文件夹和自定义文件夹，以便在渲染文档时使用。Aspose.Words 提供了强大而灵活的 API，用于处理文档中的字体。有了这些知识，您可以控制和自定义渲染文档时使用的字体源以满足您的特定需求。

### 常见问题解答

#### 问：如何在 Aspose.Words 中设置系统字体文件夹？

答：要在 Aspose.Words 中设置系统字体文件夹，您无需执行任何操作。Aspose.Words 会自动使用您操作系统上安装的系统字体。

#### 问：如何在 Aspose.Words 中设置自定义字体文件夹？

答：要在 Aspose.Words 中设置自定义字体文件夹，您可以使用`SetFontsFolders`方法`Fonts`指定自定义字体文件夹位置的类。

#### 问：我可以在 Aspose.Words 中指定多个自定义字体文件夹吗？

答：是的，您可以使用 Aspose.Words 中的`SetFontsFolders`方法`Fonts`带有文件夹位置列表的类。

#### 问：如何检查 Aspose.Words 中定义的字体文件夹？

要检查 Aspose.Words 中定义的字体文件夹，您可以使用`GetFolders`方法`Fonts`类来获取配置的字体文件夹列表。

#### 问：在 Aspose.Words 中自定义文件夹字体是否优先于系统字体？

答：是的，自定义文件夹字体在 Aspose.Words 中优先于系统字体。如果某种字体同时存在于自定义文件夹和系统字体中，Aspose.Words 将使用自定义文件夹中的版本。