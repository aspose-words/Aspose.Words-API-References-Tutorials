---
title: 忽略删除修订内的文本
linktitle: 忽略删除修订内的文本
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 的“忽略删除修订内的文本”功能。
type: docs
weight: 10
url: /zh/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的“忽略删除修订内的文本”功能。当我们在对文档进行文字处理时想要忽略删除修订内的文本时，此功能非常有用。

## Aspose.Words for .NET 库概述

在深入了解代码细节之前，让我简要介绍一下 Aspose.Words for .NET 库。它是一个功能强大的库，允许在 .NET 应用程序中创建、修改和转换 Word 文档。它为文档的文字处理提供了许多高级功能，包括修订管理。

## 了解“忽略删除修订内的文本”功能

Aspose.Words for .NET 中的“忽略删除修订内的文本”功能允许您指定在某些操作（例如查找和替换文本）期间是否应忽略删除修订内的文本。启用此功能后，操作期间不会考虑修订版内已删除的文本。

## 第 1 步：使用 Aspose.Words for .NET 创建新文档

在开始操作文档中的文本之前，我们需要使用 Aspose.Words for .NET 创建一个新文档。可以通过实例化一个来完成`Document`目的：

```csharp
Document doc = new Document();
```

## 步骤 2：将未修改的文本插入文档中

一旦我们有了文档，我们就可以使用插入未审阅的文本`DocumentBuilder`目的。例如，要插入文本“Deleted Text”，我们可以使用`Writeln`和`Write`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## 步骤 3：删除带有跟踪修订的段落

为了说明“忽略删除修订内的文本”功能的用法，我们将使用修订跟踪从文档中删除一个段落。这将使我们能够看到该功能如何影响后续操作。

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## 步骤 4：应用“忽略删除修订内的文本”功能

现在我们已经通过删除段落准备了文档，我们可以使用以下命令启用“忽略删除修订内的文本”功能`FindReplaceOptions`目的。我们将设置`IgnoreDeleted`财产给`true`：

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## 步骤 5：使用正则表达式进行查找和替换

为了对文档文本执行搜索和替换操作，我们将使用正则表达式。在我们的示例中，我们将搜索所有出现的字母“e”并将其替换为星号“* “。 。网`Regex`为此使用了类：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## 步骤 6：显示修改后的文档输出

应用搜索和替换后，我们可以使用以下命令显示文档的更改内容`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## 步骤 7：修改选项以包含已删除的文本

如果我们想在输出结果中包含已删除的文本，我们可以更改选项以不忽略已删除的文本。为此我们将设置`IgnoreDeleted`财产给`false`：

```csharp
options. IgnoreDeleted = false;
```

## 步骤8：输出删除文本的修改后的文档

更改选项后，我们可以再次执行搜索并替换以获得包含删除文本的结果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### 使用 Aspose.Words for .NET 忽略删除修订内的文本的示例源代码

以下是完整的示例源代码，演示如何使用 Aspose.Words for .NET 的“忽略删除修订内的文本”功能：

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//插入未修改的文本。
	builder.Writeln("Deleted");
	builder.Write("Text");

	//删除带有跟踪修订的第一段。
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 中的“忽略删除修订内的文本”功能。此功能对于在操作文档时忽略删除修订内的文本非常有用。我们按照分步指南创建文档、插入文本、删除带有修订跟踪的段落、应用“忽略删除修订内的文本”功能，以及执行查找和替换操作。

### 常见问题解答

#### 问：Aspose.Words for .NET 中的“忽略删除修订内的文本”功能是什么？

答：Aspose.Words for .NET 中的“忽略删除修订内的文本”功能允许您指定在某些操作（例如查找和替换文本）期间是否应忽略删除修订内的文本。启用此功能后，操作期间不会考虑修订版内已删除的文本。

#### 问：什么是 Aspose.Words for .NET？

答：Aspose.Words for .NET 是一个功能强大的库，用于创建、编辑 Word 文档并将其转换为 .NET 应用程序。它为文档的文字处理提供了许多高级功能，包括修订管理。

#### 问：如何在 Aspose.Words for .NET 中创建新文档？

答：在开始操作文档中的文本之前，您需要使用 Aspose.Words for .NET 创建一个新文档。这可以通过实例化一个来完成`Document`目的。以下是创建新文档的示例代码：

```csharp
Document doc = new Document();
```

#### 问：如何使用 Aspose.Words for .NET 将未编辑的文本插入文档中？

答：一旦有了文档，您可以使用`DocumentBuilder`目的。例如，要插入文本“已删除文本”，您可以使用`Writeln`和`Write`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### 问：如何在 Aspose.Words for .NET 中删除带有修订跟踪的段落？

答：为了说明“忽略删除修订内的文本”功能的使用，我们将使用修订跟踪从文档中删除一个段落。这将使我们能够看到该函数如何影响后续操作。

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### 问：如何在 Aspose.Words for .NET 中启用“忽略删除修订内的文本”功能？

答：现在我们已经通过删除段落准备好了文档，我们可以使用以下命令启用“忽略删除修订内的文本”功能：`FindReplaceOptions`目的。我们将设置`IgnoreDeleted`财产给`true`：

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### 问：如何在 Aspose.Words for .NET 中使用正则表达式进行搜索和替换？

答：为了对文档文本执行搜索和替换操作，我们将使用正则表达式。在我们的示例中，我们将搜索所有出现的字母“e”并将其替换为星号“* ”。我们将使用.NET`Regex`为此类：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### 问：如何在 Aspose.Words for .NET 中查看更改的文档内容？

A：应用搜索和替换后，我们可以使用以下命令显示文档的更改内容`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

#### 问：如何在 Aspose.Words for .NET 的输出结果中包含删除的文本？

答：如果我们想在输出结果中包含已删除的文本，我们可以更改选项以不忽略已删除的文本。为此，我们将设置`IgnoreDeleted`财产给`false`：

```csharp
options. IgnoreDeleted = false;
```

#### 问：如何在 Aspose.Words for .NET 中显示已编辑且已删除文本的文档？

A：更改选项后，我们可以进行新的搜索和替换，得到包含删除文本的结果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
