---
title: 设置脚注列
linktitle: 设置脚注列
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 设置 Word 文档中脚注的列数。
type: docs
weight: 10
url: /zh/net/working-with-footnote-and-endnote/set-foot-note-columns/
---

在本分步教程中，我们将指导您如何使用 Aspose.Words for .NET 设置 Word 文档中脚注的列数。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

开始之前，请确保您已经在开发环境中安装并设置了 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 第 1 步：初始化文档对象

首先，初始化`Document`通过提供源文档的路径来反对：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## 第 2 步：设置脚注列

接下来，访问`FootnoteOptions`文档的属性并设置`Columns`属性指定脚注的列数。在本例中，我们将其设置为 3 列：

```csharp
doc.FootnoteOptions.Columns = 3;
```

## 第 3 步：保存文档

最后，保存修改后的文件：

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功设置了 Word 文档中脚注的列数。

### 使用 Aspose.Words for .NET 设置脚注列的示例源代码

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Document doc = new Document(dataDir + "Document.docx");

//指定用于格式化脚注区域的列数。
doc.FootnoteOptions.Columns = 3;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。