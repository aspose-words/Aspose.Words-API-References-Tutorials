---
title: 开放式功能
linktitle: 开放式功能
second_title: Aspose.Words for .NET API 参考
description: 了解如何在 Aspose.Words for .NET 中启用和使用 Open Type 功能
type: docs
weight: 10
url: /zh/net/enable-opentype-features/open-type-features/
---

在这个综合教程中，您将学习如何在 Aspose.Words for .NET 中启用和使用 Open Type 功能。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够在 Word 文档中使用 Open Type 功能。

## 先决条件
在我们开始之前，请确保您具备以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：装入文档
首先，使用 Document 类加载文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## 第 2 步：启用开放式功能
要启用 Open Type 功能，请将 LayoutOptions 类的 TextShaperFactory 属性设置为所需文本整形器工厂的实例。在此示例中，我们使用 HarfBuzzTextShaperFactory：

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## 第 3 步：保存文档
启用 Open Type 功能后，将文档保存为所需的输出格式，例如 PDF：

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
恭喜！您已经成功学习了如何在 Aspose.Words for .NET 中启用和使用 Open Type 功能。按照分步指南并利用提供的源代码，您现在可以在 Word 文档中使用 Open Type 功能。

Open Type 功能提供增强的排版和文本整形功能，使您能够创建视觉上吸引人且具有专业外观的文档。试验不同的文本整形器工厂，探索 Open Type 功能在您的项目中的可能性。
