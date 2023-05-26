---
title: 接收字体通知
linktitle: 接收字体通知
second_title: Aspose.Words for .NET API 参考
description: 了解在使用 Aspose.Words for .NET 时如何接收丢失或替换的字体通知。
type: docs
weight: 10
url: /zh/net/working-with-fonts/receive-notifications-of-fonts/
---

在本教程中，我们将带您了解如何在使用 Aspose.Words for .NET 时接收字体通知。字体通知可让您检测和管理文档中丢失或替换的字体。我们将带您一步一步地帮助您理解和实现您的 .NET 项目中的代码。

## 先决条件
在开始之前，请确保您拥有以下物品：
- C# 编程语言的应用知识
- 项目中安装的 .NET 的 Aspose.Words 库

## 第一步：定义文档目录
首先，您需要将目录路径设置为您的 Word 文档所在的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有适当路径的代码中。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载文档并配置字体设置
接下来，我们将使用`Document`使用类和配置字体设置`FontSettings`班级。我们将设置默认字体以在缺少字体的情况下使用。

```csharp
//加载文档并配置字体设置
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

## 第 3 步：设置通知处理程序
接下来，我们将通过实现`IWarningCallback`界面。这将允许我们在保存文档时收集字体警告。

```csharp
//定义通知处理程序
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc. WarningCallback = callback;
```

## 第 4 步：应用字体设置并保存文档
最后，我们将字体设置应用于文档并保存。任何字体警告都将被我们之前定义的通知处理程序捕获。

```csharp
//应用字体设置并保存文档
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");
```

### 使用 Aspose.Words for .NET 接收字体通知的示例源代码 
```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//如果缺少任何字体，我们可以选择要使用的默认字体。
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
//为了测试，我们将设置 Aspose.Words 以仅在不存在的文件夹中查找字体。因为 Aspose.Words 不会
//在指定目录中找到任何字体，然后在渲染过程中文档中的字体将使用默认字体
//在 FontSettings.DefaultFontName 下指定的字体。我们可以使用我们的回调来接收这个子请求。
fontSettings.SetFontsFolder(string.Empty, false);
//创建一个实现 IWarningCallback 的新类，它收集文档保存期间产生的任何警告。
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");

```

## 结论
在本教程中，我们了解了如何在使用 Aspose.Words for .NET 时接收字体通知。字体通知可让您检测和管理文档中丢失或替换的字体。使用此功能可确保文档中字体的一致性，并在缺少字体的情况下采取适当的措施。
