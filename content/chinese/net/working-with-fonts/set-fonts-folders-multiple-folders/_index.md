---
title: 设置字体文件夹多个文件夹
linktitle: 设置字体文件夹多个文件夹
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 呈现文档时设置多个字体文件夹的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

在本教程中，我们将引导您逐步完成使用 Aspose.Words for .NET 渲染文档时设置多个字体文件夹的过程。我们将解释捆绑的 C# 源代码并为您提供全面的指南，以帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何指定使用 Aspose.Words for .NET 渲染文档时要使用的多个字体文件夹。

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

## 步骤 3：设置字体文件夹
现在，您可以使用`FontSettings`类和`SetFontsFolders()`方法。您可以在数组中指定要使用的字体文件夹的路径。在此示例中，我们指定了两个字体文件夹：“C:\MyFonts\“和”D:\Misc\Fonts\“。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## 步骤 4：应用字体设置
接下来，您需要使用`FontSettings`的财产`Document`班级。

```csharp
doc.FontSettings = fontSettings;
```

## 步骤 5：保存渲染的文档
最后，您可以使用`Save()`方法`Document`类。请确保指定正确的路径和文件名。

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
//渲染或嵌入字体时，字体。若要在保留系统字体源的同时添加额外的字体源，则同时使用 FontSettings.GetFontSources 和
//而是使用 FontSettings.SetFontSources。
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 在渲染文档时设置多个字体文件夹。按照本分步指南，您可以轻松指定渲染文档时要使用的多个字体文件夹。Aspose.Words 提供了强大而灵活的 API，用于处理文档中字体的文字。有了这些知识，您可以根据特定需求控制和自定义渲染文档时使用的字体源。

### 常见问题解答

#### 问：如何在 Aspose.Words 中设置多个字体文件夹？

答：要在 Aspose.Words 中设置多个字体文件夹，您可以使用`SetFontsFolders`方法`Fonts`类提供自定义字体文件夹位置的列表。

#### 问：设置多个字体文件夹会影响用 Aspose.Words 处理的所有文档吗？

答：是的，设置多个字体文件夹会影响使用 Aspose.Words 处理的所有文档。一旦您定义了字体文件夹，Aspose.Words 将使用这些位置在所有文档中搜索字体。

#### 问：我可以在 Aspose.Words 中定义多少个字体文件夹？

答：您可以在 Aspose.Words 中根据需要定义任意数量的字体文件夹。对于您可以定义的字体文件夹数量没有具体限制。

#### 问：如何检查 Aspose.Words 中定义的字体文件夹？

答：要检查 Aspose.Words 中定义的字体文件夹，您可以使用`GetFolders`方法`Fonts`类来获取配置的字体文件夹的位置。

#### 问：字体文件夹需要包含特定的字体吗？

答：是的，字体文件夹应该包含您想要在 Word 文档中使用的字体。Aspose.Words 将在处理文档时在指定的文件夹中查找字体。