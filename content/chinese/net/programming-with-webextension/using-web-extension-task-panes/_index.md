---
title: 使用 Web 扩展任务窗格
linktitle: 使用 Web 扩展任务窗格
second_title: Aspose.Words 文档处理 API
description: 在本详细的分步教程中了解如何使用 Aspose.Words for .NET 在 Word 文档中添加和配置 Web 扩展任务窗格。
type: docs
weight: 10
url: /zh/net/programming-with-webextension/using-web-extension-task-panes/
---
## 介绍

欢迎阅读本深入教程，了解如何使用 Aspose.Words for .NET 在 Word 文档中使用 Web 扩展任务窗格。如果您曾经想使用交互式任务窗格增强 Word 文档，那么您来对地方了。本指南将引导您完成无缝实现此目标的每个步骤。

## 先决条件

在深入研究之前，请确保您已准备好所需的一切：

-  Aspose.Words for .NET：您可以下载它[这里](https://releases.aspose.com/words/net/).
- .NET 开发环境：Visual Studio 或您喜欢的任何其他 IDE。
- C# 基础知识：这将帮助您理解代码示例。
-  Aspose.Words 许可证：您可以购买一个[这里](https://purchase.aspose.com/buy)或获得临时执照[这里](https://purchase.aspose.com/temporary-license/).

## 导入命名空间

在开始编码之前，请确保已在项目中导入以下命名空间：

```csharp
using Aspose.Words;
using Aspose.Words.WebExtensions;
```

## 循序渐进指南

现在，让我们将该过程分解为易于遵循的步骤。

### 步骤 1：设置文档目录

首先，我们需要设置文档目录的路径。这是保存 Word 文档的位置。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`使用您的文档文件夹的实际路径。

### 步骤 2：创建新文档

接下来，我们将使用 Aspose.Words 创建一个新的 Word 文档。

```csharp
Document doc = new Document();
```

这行初始化了`Document`类，代表一个 Word 文档。

### 步骤 3：添加任务窗格

现在，我们将在文档中添加一个任务窗格。任务窗格可用于在 Word 文档中提供附加功能和工具。

```csharp
TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);
```

在这里，我们创建一个新的`TaskPane`对象并将其添加到文档的`WebExtensionTaskPanes`收藏。

### 步骤 4：配置任务窗格

为了使我们的任务窗格可见并设置其属性，我们使用以下代码：

```csharp
taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

- `DockState`设置任务窗格的显示位置。在本例中，它位于右侧。
- `IsVisible`确保任务窗格可见。
- `Width`设置任务窗格的宽度。

### 步骤 5：设置 Web 扩展参考

接下来，我们设置 Web 扩展参考，其中包括 ID、版本、商店类型和商店。

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

- `Id`是网络扩展的唯一标识符。
- `Version`指定扩展的版本。
- `StoreType`表示商店的类型（在本例中为OMEX）。
- `Store`指定商店的语言/文化代码。

### 步骤 6：向 Web 扩展添加属性

您可以向您的 Web 扩展添加属性来定义其行为或内容。

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
```

在这里我们添加一个名为`mailchimpCampaign`.

### 步骤 7：绑定 Web 扩展

最后，我们为 Web 扩展添加绑定。绑定允许您将扩展链接到文档的特定部分。

```csharp
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545", WebExtensionBindingType.Text, "194740422"));
```

- `UnnamedBinding_0_1506535429545`是绑定的名称。
- `WebExtensionBindingType.Text`表示绑定是文本类型。
- `194740422`是扩展所绑定的文档部分的 ID。

### 步骤 8：保存文档

一切设置完成后，保存您的文档。

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

此行将文档以给定的文件名保存到指定的目录。

### 步骤 9：加载和显示任务窗格信息

为了验证和显示任务窗格信息，我们加载文档并遍历任务窗格。

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");

Console.WriteLine("Task panes sources:\n");

foreach (TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
    WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;
    Console.WriteLine($"Provider: \"{reference.Store}\", version: \"{reference.Version}\", catalog identifier: \"{reference.Id}\";");
}
```

此代码加载文档并在控制台中打印每个任务窗格的提供程序、版本和目录标识符。

## 结论

就这样！您已成功使用 Aspose.Words for .NET 在 Word 文档中添加并配置了 Web 扩展任务窗格。此强大功能可直接在文档中提供附加功能，从而显著增强您的 Word 文档。 

## 常见问题解答

### Word 中的任务窗格是什么？
任务窗格是一种界面元素，它在 Word 文档中提供附加工具和功能，增强用户交互和工作效率。

### 我可以自定义任务窗格的外观吗？
是的，您可以通过设置以下属性来自定义任务窗格的外观`DockState`, `IsVisible`， 和`Width`.

### 什么是 Web 扩展属性？
Web 扩展属性是您可以添加到 Web 扩展以定义其行为或内容的自定义属性。

### 如何将 Web 扩展绑定到文档的一部分？
您可以使用以下方式将 Web 扩展绑定到文档的某个部分：`WebExtensionBinding`类，指定绑定类型和目标ID。

### 在哪里可以找到有关 Aspose.Words for .NET 的更多信息？
您可以找到详细的文档[这里](https://reference.aspose.com/words/net/).