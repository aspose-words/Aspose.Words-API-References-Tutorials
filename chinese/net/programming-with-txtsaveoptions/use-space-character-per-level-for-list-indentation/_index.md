---
title: 每级使用空格字符进行列表缩进
linktitle: 每级使用空格字符进行列表缩进
second_title: Aspose.Words for .NET API 参考
description: 在 Aspose.Words for .NET 中使用每级空格字符进行列表缩进的分步指南。轻松创建结构良好的 Word 文档。
type: docs
weight: 10
url: /zh/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words for .NET 是一个功能强大的库，用于在 C# 应用程序中创建、编辑和操作 Word 文档。 Aspose.Words 提供的功能之一是可以在每一级使用一个空格字符来缩进列表。在本指南中，我们将向您展示如何使用 Aspose.Words for .NET 的 C# 源代码来实现此功能。

## 了解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库非常重要。 Aspose.Words 是一个流行的库，它使 Word 文档的处理变得简单而高效。它提供了广泛的创建、修改和操作 Word 文档的功能，包括列表和缩进的管理。

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

在此示例中，我们创建一个新文档并使用 DocumentBuilder 添加文本并创建具有三级缩进的列表。我们在列表中添加了三个项目，每个项目都缩进了一个额外的级别。

## 每级使用一个空格字符进行列表缩进

添加内容后，我们现在可以使用每级一个空格字符来配置列表的缩进。为此，我们使用 TxtSaveOptions 类，并将 ListIndentation.Count 属性设置为缩进级别数，将 ListIndentation.Character 属性设置为要使用的空格字符。就是这样：

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

在此示例中，我们创建 TxtSaveOptions 的实例并将 ListIndentation.Count 属性设置为 3 以指示列表中存在三个缩进级别。我们还将 ListIndentation.Character 属性设置为要用于缩进的空格字符 (' ')。

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

             //每级使用一个空格字符进行列表缩进
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

在本指南中，我们解释了如何使用 Aspose.Words for .NET 来应用“每级使用一个空格字符进行列表缩进”功能。通过按照提供的步骤并使用提供的 C# 源代码，您可以轻松配置 Word 文档中列表的缩进，每级使用一个空格字符。 Aspose.Words 为文本格式设置和列表管理提供了巨大的灵活性和强大功能，允许您在 C# 应用程序中创建结构良好的文档。

### 经常问的问题

#### 问：什么是 Aspose.Words for .NET？
Aspose.Words for .NET 是一个功能强大的库，用于在 C# 应用程序中创建、编辑和操作 Word 文档。它提供了许多用于处理 Word 文档的功能，包括能够在每一级使用一个空格来缩进列表。

#### 问：如何使用 Aspose.Words for .NET 在每一级使用一个空格来进行列表缩进？
您可以按照以下步骤在每一级使用一个空格来缩进列表：

使用创建一个新文档`Document`班级。

使用`DocumentBuilder`类向文档添加内容并创建具有多级缩进的列表。

添加内容并配置列表缩进后，请使用`TxtSaveOptions`类并设置`ListIndentation.Count`属性与缩进级别的数量和`ListIndentation.Character`空间上的属性（`' '`）来使用。

使用指定选项保存文档`Save`的方法`Document`班级。

#### 问：Aspose.Words 是否支持其他字符进行列表缩进？
是的，Aspose.Words 支持其他字符来缩进列表。您可以使用非空白字符，例如制表符 (`'\t'` ) 或其他特殊字符，通过设置`ListIndentation.Character`属性到所需的角色。

#### 问：是否可以自定义列表缩进每级的空格数？
是的，您可以通过更改列表缩进的值来自定义每级的空格数`ListIndentation.Count`财产在`TxtSaveOptions`班级。您可以指定每个缩进级别所需的空格数。

#### 问：Aspose.Words 还提供哪些其他列表管理功能？
Aspose.Words 提供了许多用于管理 Word 文档中的列表的功能。您可以创建编号列表或项目符号列表、设置缩进级别、自定义列表样式、添加列表项等等。