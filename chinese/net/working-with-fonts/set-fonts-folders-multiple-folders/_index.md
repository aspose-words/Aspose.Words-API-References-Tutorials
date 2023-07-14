---
title: 设置字体文件夹多个文件夹
linktitle: 设置字体文件夹多个文件夹
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 渲染文档时设置多个字体文件夹的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 渲染文档时设置多个字体文件夹的分步过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解在使用 Aspose.Words for .NET 渲染文档时如何指定要使用的多个字体文件夹。

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

## 第三步：设置字体文件夹
现在您可以使用以下命令设置多个字体文件夹`FontSettings`类和`SetFontsFolders()`方法。您可以指定要在数组中使用的字体文件夹的路径。在此示例中，我们指定了两个字体文件夹：“C:\MyFonts\”和“D:\Misc\Fonts\”。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## 第 4 步：应用字体设置
接下来，您需要使用以下命令将字体设置应用到您的文档`FontSettings`的财产`Document`班级。

```csharp
doc.FontSettings = fontSettings;
```

## 第5步：保存渲染的文档
最后，您可以使用以下命令将渲染的文档保存到文件中`Save()`的方法`Document`班级。请务必指定正确的路径和文件名。

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
//相反，FontSettings.SetFontSources。
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## 结论
在本教程中，我们学习了如何在使用 Aspose.Words for .NET 渲染文档时设置多个字体文件夹。通过遵循此分步指南，您可以轻松指定渲染文档时要使用的多个字体文件夹。 Aspose.Words 提供了强大而灵活的 API，用于文档中字体的文字处理。有了这些知识，您就可以控制和自定义在根据您的特定需求渲染文档时使用的字体源。

### 常见问题解答

#### 问：如何在 Aspose.Words 中设置多个字体文件夹？

答：要在Aspose.Words中设置多个字体文件夹，您可以使用`SetFontsFolders`的方法`Fonts`提供自定义字体文件夹位置列表的类。

#### 问：设置多个字体文件夹是否会影响使用 Aspose.Words 处理的所有文档？

答：是的，设置多个字体文件夹会影响使用 Aspose.Words 处理的所有文档。定义字体文件夹后，Aspose.Words 将使用这些位置在所有文档中搜索字体。

#### 问：我可以在 Aspose.Words 中定义多少个字体文件夹？

答：您可以在 Aspose.Words 中根据需要定义任意数量的字体文件夹。您可以定义的字体文件夹的数量没有具体限制。

#### 问：如何查看 Aspose.Words 中定义的字体文件夹？

答：要检查 Aspose.Words 中定义的字体文件夹，您可以使用`GetFolders`的方法`Fonts`类来获取配置的字体文件夹的位置。

#### 问：字体文件夹是否需要包含特定字体？

答：是的，字体文件夹应包含您要在 Word 文档中使用的字体。 Aspose.Words在处理文档时将在指定文件夹中查找字体。