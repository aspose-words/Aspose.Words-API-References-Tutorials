---
title: 每级使用制表符进行列表缩进
linktitle: 每级使用制表符进行列表缩进
second_title: Aspose.Words for .NET API 参考
description: 了解如何在 Aspose.Words for .NET 中使用带有制表符功能的缩进列表。使用这个强大的功能可以节省时间并改善您的工作流程。
type: docs
weight: 10
url: /zh/net/programming-with-txtsaveoptions/use-tab-character-per-level-for-list-indentation/
---

在本教程中，我们将探索 Aspose.Words for .NET 中为“每级使用一个制表符用于列表缩进”功能提供的 C# 源代码。此功能允许您将制表符应用于每个级别的缩进列表，从而提供更大的灵活性和对文档外观的控制。

## 第 1 步：设置环境

在您开始之前，请确保您已经使用 Aspose.Words for .NET 设置了您的开发环境。确保您已经添加了必要的引用并导入了适当的命名空间。

## 第 2 步：创建文档和生成器

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

在这一步中，我们创建一个新的`Document`对象和关联的`DocumentBuilder`目的。这些对象将允许我们操作和生成我们的文档。

## 第 3 步：创建具有三级缩进的列表

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

在此步骤中，我们使用列表编号的默认格式`ApplyNumberDefault()`列表格式化程序的方法。接下来，我们使用文档生成器的将三个项目添加到我们的列表中`Writeln()`和`Write()`方法。我们使用`ListIndent()`在每个级别增加缩进的方法。

## 第 4 步：配置录制选项

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';
```

在此步骤中，我们配置用于保存文档的选项。我们创造一个新的`TxtSaveOptions`对象并设置`ListIndentation.Count`属性设置为 1 以指定每个缩进级别的制表符数。我们还设置了`ListIndentation.Character`属性为 '\t' 以指定我们要使用制表符。

## 第 5 步：保存文档

```csharp
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
```

在这最后一步中，我们使用指定的保存选项保存文档。我们使用`Save()`传递输出文件的完整路径和保存选项的文档方法。


现在您可以运行源代码以使用制表符生成带有列表缩进的文档。输出文件将保存在名称为“WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt”的指定目录中。

### Aspose.Words for .NET 的列表缩进功能每级使用一个制表符的示例代码源：

```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//创建具有三级缩进的列表
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");

TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);

```

现在您已经完成使用制表符生成带有列表缩进的文档，您可以使用 Markdown 来格式化您的文章内容。请务必使用适当的格式标签来突出标题、副标题和包含的源代码。