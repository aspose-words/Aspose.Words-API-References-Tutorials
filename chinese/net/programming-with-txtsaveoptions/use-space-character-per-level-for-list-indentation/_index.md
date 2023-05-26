---
title: 每级使用空格字符进行列表缩进
linktitle: 每级使用空格字符进行列表缩进
second_title: Aspose.Words for .NET API 参考
description: 在 Aspose.Words for .NET 中使用每个级别的空格字符进行列表缩进的分步指南。轻松创建结构良好的 Word 文档。
type: docs
weight: 10
url: /zh/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words for .NET 是一个强大的库，用于在 C# 应用程序中创建、编辑和操作 Word 文档。 Aspose.Words 提供的功能之一是可以在每一层使用一个空格字符来缩进列表。在本指南中，我们将向您展示如何使用 Aspose.Words for .NET 的 C# 源代码来实现此功能。

## 理解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库很重要。 Aspose.Words 是一个流行的库，它使处理 Word 文档变得简单而高效。它为创建、修改和操作 Word 文档提供了广泛的功能，包括列表和缩进的管理。

## 创建文档并添加内容

第一步是创建一个新文档并向其中添加内容。使用 Document 类创建一个新的文档实例。然后使用 DocumentBuilder 类添加文本并创建具有多级缩进的列表。这是一个例子：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//创建具有三级缩进的列表
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

在此示例中，我们创建一个新文档并使用 DocumentBuilder 添加文本并创建一个具有三级缩进的列表。我们向列表中添加了三个项目，每个项目都缩进了一个额外的级别。

## 每个级别使用一个空格字符进行列表缩进

添加内容后，我们现在可以使用每个级别一个空格字符来配置列表的缩进。为此，我们使用 TxtSaveOptions 类，并将 ListIndentation.Count 属性设置为缩进级别数，并将 ListIndentation.Character 属性设置为要使用的空格字符。就是这样：

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

在此示例中，我们创建了一个 TxtSaveOptions 实例，并将 ListIndentation.Count 属性设置为 3，以指示列表中有三级缩进。我们还将 ListIndentation.Character 属性设置为要用于缩进的空格字符 (' ')。

### Aspose.Words for .NET 的“每级使用一个空格字符进行列表缩进”功能的示例源代码

以下是 Aspose.Words for .NET 的“每级使用一个空格字符进行列表缩进”功能的完整示例源代码：

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             //文档目录的路径
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             //创建文档并添加内容
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             //创建具有三级缩进的列表
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             //每个级别使用一个空格字符进行列表缩进
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             //使用指定选项保存文档
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## 结论

在本指南中，我们解释了如何使用 Aspose.Words for .NET 应用“每级使用一个空格字符进行列表缩进”功能。按照提供的步骤并使用提供的 C# 源代码，您可以轻松地配置 Word 文档中列表的缩进，每个级别使用一个空格字符。 Aspose.Words 为处理文本格式和列表管理提供了巨大的灵活性和强大的功能，允许您在 C# 应用程序中创建结构良好的文档。