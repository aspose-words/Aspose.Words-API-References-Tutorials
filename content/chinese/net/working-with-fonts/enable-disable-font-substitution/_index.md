---
title: 启用禁用字体替换
linktitle: 启用禁用字体替换
second_title: Aspose.Words 文档处理 API
description: 在本教程中，学习如何使用 Aspose.Words for .NET 在 Word 文档中启用或禁用字体替换。
type: docs
weight: 10
url: /zh/net/working-with-fonts/enable-disable-font-substitution/
---
在本教程中，我们将引导您了解如何在使用适用于 .NET 的 Aspose.Words 库呈现 Word 文档时启用或禁用字体替换。启用或禁用字体替换允许您控制是否自动用默认字体替换缺失的字体。我们将逐步指导您理解和实现 .NET 项目中的代码。

## 先决条件
开始之前，请确保您拥有以下物品：
- 具备 C# 编程语言的工作知识
- 项目中安装的 .NET Aspose.Words 库
- 想要使用或不使用字体替换来呈现的 Word 文档

## 步骤1：定义文档目录
首先，您需要将目录路径设置为 Word 文档的位置。替换`"YOUR DOCUMENT DIRECTORY"`在代码中使用适当的路径。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：上传文档并配置字体设置
接下来，我们将加载要渲染的 Word 文档，并创建`FontSettings`类来处理字体设置。我们将通过在`DefaultFontName`并禁用字体信息覆盖`Enabled`设置`false`.

```csharp
//加载文档
Document doc = new Document(dataDir + "Rendering.docx");

//配置字体设置
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

//将字体设置应用到文档
doc.FontSettings = fontSettings;
```

## 步骤 3：保存渲染的文档
最后，我们将保存渲染的文档，它将遵循定义的字体覆盖设置。

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### 使用 Aspose.Words for .NET 启用禁用字体替换的示例源代码 

```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## 结论
在本教程中，我们了解了如何在使用 Aspose.Words for .NET 渲染 Word 文档时启用或禁用字体替换。通过控制字体替换，您可以影响渲染文档中缺失字体的处理方式。请随时使用此功能自定义 Word 文档中的字体管理。

### 常见问题解答

#### 问：如何使用 Aspose.Words 在 Word 文档中启用字体替换？

答：要使用 Aspose.Words 在 Word 文档中启用字体替换，您可以使用 API 指定在所需字体不可用时使用的替换字体。这将确保一致的文本可视化，即使没有原始字体。

#### 问：是否可以使用 Aspose.Words 禁用 Word 文档中的字体替换？

答：是的，使用 Aspose.Words 您可以在 Word 文档中禁用字体替换。通过使用 API，您可以阻止 Word 用其他字体替换所需字体，从而保持文本的原始外观。

#### 问：如果在 Word 文档中替换时缺少所需字体，会发生什么情况？

答：当 Word 文档在替换过程中缺少所需字体时，Aspose.Words 可以检测到此问题并为您提供修复选项。您可以选择用替代字体替换缺失的字体，或者在文档中包含缺失的字体，以确保正确查看。

#### 问：使用 Aspose.Words 替换 Word 文档时如何处理缺失的字体？

答：要处理使用 Aspose.Words 替换 Word 文档时丢失的字体，您可以使用 API 检测丢失的字体并提供解决方案。您可以根据需要选择用其他字体替换丢失的字体或在文档中包含丢失的字体。

#### 问：控制 Word 文档中的字体替换重要吗？

答：是的，控制 Word 文档中的字体替换对于保持文本的视觉完整性非常重要。通过使用 Aspose.Words 启用或禁用字体替换，您可以确保使用所需的字体并避免出现字体缺失或替换的问题。