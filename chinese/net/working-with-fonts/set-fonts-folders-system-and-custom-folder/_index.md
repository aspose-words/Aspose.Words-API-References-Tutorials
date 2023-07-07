---
title: 设置字体文件夹系统和自定义文件夹
linktitle: 设置字体文件夹系统和自定义文件夹
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 渲染文档时设置系统和自定义字体文件夹的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 渲染文档时设置系统字体文件夹和自定义文件夹的分步过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何指定多个字体文件夹，包括系统文件夹和自定义文件夹，以便在使用 Aspose.Words for .NET 渲染文档时使用。

## 第1步：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑后的渲染文档的位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载要渲染的文档
然后您可以使用以下命令加载要渲染的文档`Document`班级。请务必指定正确的文档路径。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步骤 3：设置系统和自定义字体文件夹
现在您可以使用以下命令设置系统字体文件夹和自定义文件夹`FontSettings`类和`SetFontsSources()`方法。首先，您需要使用以下命令检索依赖于环境的字体源列表`GetFontsSources()`并将其存储在列表中。然后你可以创建一个新的实例`FolderFontSource`指定包含字体的自定义文件夹的路径。将此实例添加到现有字体源列表中。最后，使用`SetFontsSources()`使用新列表更新字体源。

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## 第 4 步：应用字体设置
接下来，您需要使用以下命令将字体设置应用到您的文档`FontSettings`的财产`Document`班级。

```csharp
doc.FontSettings = fontSettings;
```

## 第5步：保存渲染的文档
最后，您可以将渲染的文档保存到文件中

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
//检索默认搜索的与环境相关的字体源数组。
//例如，这将包含 Windows 计算机上的“Windows\Fonts\”源。
//我们将此数组添加到新列表中，以便更轻松地添加或删除字体条目。
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
//添加一个新的文件夹源，它将指示 Aspose.Words 在以下文件夹中搜索字体。
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
//将包含我们的字体的自定义文件夹添加到现有字体源列表中。
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## 结论
在本教程中，我们学习了如何在使用 Aspose.Words for .NET 渲染文档时设置系统字体文件夹和自定义文件夹。通过遵循此分步指南，您可以轻松指定在渲染文档时使用的多个字体文件夹，包括系统文件夹和自定义文件夹。 Aspose.Words 提供了强大且灵活的 API，用于处理文档中的字体。有了这些知识，您就可以控制和自定义在根据您的特定需求渲染文档时使用的字体源。

### 常见问题解答

#### 问：如何在 Aspose.Words 中设置系统字体文件夹？

答：要在 Aspose.Words 中设置系统字体文件夹，您无需执行任何操作。 Aspose.Words 自动使用操作系统上安装的系统字体。

#### 问：如何在 Aspose.Words 中设置自定义字体文件夹？

答：要在 Aspose.Words 中设置自定义字体文件夹，您可以使用`SetFontsFolders`的方法`Fonts`指定自定义字体文件夹位置的类。

#### 问：我可以在 Aspose.Words 中指定多个自定义字体文件夹吗？

答：是的，您可以使用 Aspose.Words 中指定多个自定义字体文件夹`SetFontsFolders`的方法`Fonts`带有文件夹位置列表的类。

#### 问：如何查看 Aspose.Words 中定义的字体文件夹？

要检查 Aspose.Words 中定义的字体文件夹，您可以使用`GetFolders`的方法`Fonts`类来获取配置的字体文件夹的列表。

#### 问：Aspose.Words 中自定义文件夹字体是否优先于系统字体？

答：是的，在 Aspose.Words 中自定义文件夹字体优先于系统字体。如果自定义文件夹和系统字体中都存在某种字体，Aspose.Words 将使用自定义文件夹中的版本。