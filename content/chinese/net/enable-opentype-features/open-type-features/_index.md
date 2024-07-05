---
title: 开放式特色
linktitle: 开放式特色
second_title: Aspose.Words 文档处理 API
description: 了解如何在 Aspose.Words for .NET 中启用和使用 Open Type 功能
type: docs
weight: 10
url: /zh/net/enable-opentype-features/open-type-features/
---

在本综合教程中，您将学习如何在 Aspose.Words for .NET 中启用和使用 Open Type 功能。我们将指导您完成整个过程并为您提供必要的 C# 代码片段。在本指南结束时，您将能够在 Word 文档中使用 Open Type 功能。

## 先决条件
在开始之前，请确保您满足以下先决条件：
- 您的系统上安装了 Aspose.Words for .NET 库。

## 步骤 1：加载文档
首先，使用 Document 类加载文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## 第 2 步：启用 Open Type 功能
要启用 Open Type 功能，请将 LayoutOptions 类的 TextShaperFactory 属性设置为所需文本整形器工厂的实例。在此示例中，我们使用 HarfBuzzTextShaperFactory：

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## 步骤 3：保存文档
启用 Open Type 功能后，以所需的输出格式保存文档，例如 PDF：

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### 使用 Aspose.Words for .NET 的开放类型功能示例源代码
以下是在 Aspose.Words for .NET 中使用 Open Type 功能的完整源代码：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## 结论
恭喜！您已成功了解如何在 Aspose.Words for .NET 中启用和使用 Open Type 功能。通过遵循分步指南并利用提供的源代码，您现在可以在 Word 文档中使用 Open Type 功能。

Open Type 功能提供增强的排版和文本塑造功能，让您可以创建具有视觉吸引力和专业外观的文档。尝试使用不同的文本塑造器工厂，并探索 Open Type 功能在您的项目中的可能性。

### 常见问题解答

#### 问：如何在 Aspose.Words for .NET 中启用 OpenType 功能？

答：要在 Aspose.Words for .NET 中启用 OpenType 功能，您需要按照教程中提到的步骤进行操作。

#### 问：Aspose.Words for .NET 支持哪些 OpenType 功能？

答：Aspose.Words for .NET 支持多种 OpenType 功能，例如连字、字形变化、上下文替换等。

#### 问：如何检查特定字体是否支持 OpenType 功能？

答：您可以使用以下方法检查特定字体是否支持 OpenType 功能`Font.OpenTypeFeatures`Aspose.Words for .NET 中的方法。

#### 问：Aspose.Words for .NET 还支持哪些其他文本格式化功能？

答：除了 OpenType 功能外，Aspose.Words for .NET 还支持其他文本格式化功能，如格式化段落、创建表格、添加图像等。

#### 问：我可以在所有版本的 Aspose.Words for .NET 中使用 OpenType 功能吗？

答：较新版本的 Aspose.Words for .NET 支持 OpenType 功能。请确保您使用兼容版本才能享受这些功能。