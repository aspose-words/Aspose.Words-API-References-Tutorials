---
title: 设置优先级字体文件夹
linktitle: 设置优先级字体文件夹
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 渲染文档时优先设置字体文件夹的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fonts/set-fonts-folders-with-priority/
---

在本教程中，我们将引导您逐步完成使用 Aspose.Words for .NET 渲染文档时设置优先字体文件夹的过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解在使用 Aspose.Words for .NET 渲染文档时如何指定具有自定义搜索优先级的多个字体文件夹。

## 第1步：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑后的渲染文档的位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤2：设置优先字体文件夹
然后您可以使用以下命令设置优先字体文件夹`FontSettings`类和`SetFontsSources()`方法。您可以使用以下实例指定多个字体源`SystemFontSource`和`FolderFontSource`。在本例中，我们定义了两个字体源：默认的系统字体源和优先级为1的自定义字体文件夹。

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## 第 3 步：加载要渲染的文档
现在您可以使用以下命令加载要渲染的文档`Document`班级。请务必指定正确的文档路径。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步骤 4：保存渲染的文档
最后，您可以使用以下命令将渲染的文档保存到文件中`Save()`的方法`Document`班级。请务必指定正确的路径和文件名。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### 使用 Aspose.Words for .NET 设置优先级字体文件夹的示例源代码 
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
在本教程中，我们学习了如何在使用 Aspose.Words for .NET 渲染文档时优先设置字体文件夹。通过遵循此分步指南，您可以在渲染文档时轻松指定具有自定义搜索优先级的多个字体文件夹。 Aspose.Words 提供了强大且灵活的 API，用于处理文档中的字体。有了这些知识，您就可以控制和自定义在根据您的特定需求渲染文档时使用的字体源。

### 常见问题解答

#### 问：如何在 Aspose.Words 中设置优先字体文件夹？

答：要在 Aspose.Words 中设置优先字体文件夹，您可以使用`SetFontsFoldersWithPriority`的方法`Fonts`通过指定字体文件夹位置及其优先级顺序来定义类。

#### 问：如果一种字体存在于多个具有不同优先级的文件夹中，会发生什么情况？

答：如果一种字体存在于多个具有不同优先级的文件夹中，Aspose.Words 在处理文档时将使用具有最高优先级的文件夹中的版本。

#### 问：我可以在 Aspose.Words 中指定多个具有相同优先级的字体文件夹吗？

答：是的，您可以在 Aspose.Words 中指定多个具有相同优先级的字体文件夹。在文档中搜索字体时，Aspose.Words 会同等优先考虑它们。

#### 问：如何查看Aspose.Words中定义的优先字体文件夹？

答：要检查 Aspose.Words 中优先定义的字体文件夹，您可以使用`GetFolders`的方法`Fonts`类来获取已配置字体文件夹的列表，包括它们的优先级顺序。

#### 问：在Aspose.Words中设置优先字体文件夹有什么用？

答：在Aspose.Words中设置优先字体文件夹可以让您控制Word文档中字体的搜索顺序。这有助于您确保使用所需的字体并避免不必要的字体替换问题。