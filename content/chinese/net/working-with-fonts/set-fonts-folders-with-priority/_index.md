---
title: 设置字体文件夹优先级
linktitle: 设置字体文件夹优先级
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 呈现文档时优先设置字体文件夹的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-fonts-folders-with-priority/
---

在本教程中，我们将引导您逐步完成使用 Aspose.Words for .NET 渲染文档时设置具有优先级的字体文件夹的过程。我们将解释捆绑的 C# 源代码并为您提供全面的指南，以帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何在使用 Aspose.Words for .NET 渲染文档时指定具有自定义搜索优先级的多个字体文件夹。

## 步骤1：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑后的渲染文档的位置。将“YOUR DOCUMENTS DIRECTORY”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：设置优先字体文件夹
然后，您可以使用`FontSettings`类和`SetFontsSources()`方法。您可以使用以下实例指定多个字体源`SystemFontSource`和`FolderFontSource`在这个例子中，我们定义了两个字体源：默认的系统字体源和优先级为1的自定义字体文件夹。

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## 步骤 3：加载要渲染的文档
现在，您可以使用`Document`类。请确保指定正确的文档路径。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步骤 4：保存渲染的文档
最后，您可以使用`Save()`方法`Document`类。请确保指定正确的路径和文件名。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### 使用 Aspose.Words for .NET 设置字体文件夹优先级的示例源代码 
```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 在渲染文档时设置字体文件夹的优先级。按照本分步指南，您可以在渲染文档时轻松指定具有自定义搜索优先级的多个字体文件夹。Aspose.Words 提供了强大而灵活的 API，用于处理文档中字体的文字。有了这些知识，您可以根据特定需求控制和自定义渲染文档时使用的字体源。

### 常见问题解答

#### 问：如何在 Aspose.Words 中设置优先字体文件夹？

答：要在 Aspose.Words 中设置字体文件夹的优先级，您可以使用`SetFontsFoldersWithPriority`方法`Fonts`通过指定字体文件夹位置及其优先级顺序来分类。

#### 问：如果一种字体存在于多个具有不同优先级的文件夹中，会发生什么情况？

答：如果字体存在于具有不同优先级的多个文件夹中，Aspose.Words 将在处理文档时使用优先级最高的文件夹中的版本。

#### 问：我可以在 Aspose.Words 中指定具有相同优先级的多个字体文件夹吗？

答：是的，您可以在 Aspose.Words 中指定多个具有相同优先级的字体文件夹。Aspose.Words 在您的文档中搜索字体时会以相同的优先级考虑所有字体文件夹。

#### 问：如何检查 Aspose.Words 中优先定义的字体文件夹？

答：要检查 Aspose.Words 中优先定义的字体文件夹，您可以使用`GetFolders`方法`Fonts`类来获取配置的字体文件夹列表，包括它们的优先级顺序。

#### 问：在Aspose.Words中设置字体文件夹优先有什么用？

答：在 Aspose.Words 中设置字体文件夹的优先级，可以控制 Word 文档中字体的搜索顺序。这有助于确保使用所需的字体，并避免不必要的字体替换问题。