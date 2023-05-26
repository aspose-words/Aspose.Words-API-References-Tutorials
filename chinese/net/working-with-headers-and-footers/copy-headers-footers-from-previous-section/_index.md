---
title: 从上一节复制页眉页脚
linktitle: 从上一节复制页眉页脚
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 复制 Word 文档上一节中的页眉和页脚。
type: docs
weight: 10
url: /zh/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

在本分步教程中，我们将指导您如何使用 Aspose.Words for .NET 在 Word 文档中复制上一节的页眉和页脚。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

要开始，请确保您已在开发环境中安装和设置 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 第 1 步：访问上一节

首先，通过访问`PreviousSibling`当前部分的属性：

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## 第 2 步：检查上一节

接下来，检查上一节是否存在。如果没有前面的部分，我们简单地返回：

```csharp
if (previousSection == null)
    return;
```

## 第 3 步：清除和复制页眉和页脚

要将上一节的页眉和页脚复制到当前节，我们清除当前节中现有的页眉和页脚，然后遍历上一节的页眉和页脚以将克隆的副本添加到当前节：

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## 第 4 步：保存文档

最后，保存修改后的文件：

```csharp
doc.Save("OutputDocument.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功地将页眉和页脚从上一节复制到 Word 文档的当前节。

### 使用 Aspose.Words for .NET 从上一节复制页眉页脚的示例源代码

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。