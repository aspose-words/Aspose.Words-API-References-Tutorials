---
title: 忽略删除修订版本内的文本
linktitle: 忽略删除修订版本内的文本
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 的“忽略删除修订中的文本”功能。
type: docs
weight: 10
url: /zh/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的“忽略删除修订中的文本”功能。当我们想要在对文档进行文字处理时忽略删除修订中的文本时，此功能很有用。

## Aspose.Words for .NET 库概述

在深入介绍代码细节之前，让我先简单介绍一下 Aspose.Words for .NET 库。这是一个功能强大的库，允许在 .NET 应用程序中创建、修改和转换 Word 文档。它为文档的文字处理提供了许多高级功能，包括修订管理。

## 了解“忽略删除修订中的文本”功能

Aspose.Words for .NET 中的“忽略删除修订版本中的文本”功能允许您指定是否应在某些操作（例如查找和替换文本）期间忽略删除修订版本中的文本。启用此功能后，操作期间不会考虑修订版本中的已删除文本。

## 步骤 1：使用 Aspose.Words for .NET 创建新文档

在开始处理文档中的文本之前，我们需要使用 Aspose.Words for .NET 创建一个新文档。可以通过实例化`Document`目的：

```csharp
Document doc = new Document();
```

## 步骤 2：将未修订的文本插入文档

一旦我们有了文档，我们就可以使用`DocumentBuilder`对象。例如，要插入文本“已删除文本”，我们可以使用`Writeln`和`Write`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## 步骤 3：删除带有跟踪修订的段落

为了说明“忽略删除修订中的文本”功能的使用，我们将使用修订跟踪从文档中删除一个段落。这将使我们能够看到此功能如何影响后续操作。

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## 步骤 4：应用“忽略删除修订中的文本”功能

现在我们已经通过删除一个段落来准备我们的文档，我们可以使用`FindReplaceOptions`对象。我们将设置`IgnoreDeleted`财产`true`：

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## 步骤 5：使用正则表达式进行查找和替换

要对文档文本执行搜索和替换操作，我们将使用正则表达式。在我们的示例中，我们将搜索字母“e”的所有出现位置，并将其替换为星号“* “。 。网`Regex`用于此目的的类：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## 步骤 6：显示修改后的文档输出

应用搜索和替换后，我们可以使用`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## 步骤 7：修改选项以包含已删除的文本

如果我们想在输出结果中包含已删除的文本，我们可以更改选项以不忽略已删除的文本。为此，我们将设置`IgnoreDeleted`财产`false`：

```csharp
options. IgnoreDeleted = false;
```

## 步骤 8：输出已删除文本的修改文档

更改选项后，我们可以再次执行搜索和替换以获得包含已删除文本的结果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### 使用 Aspose.Words for .NET 忽略删除修订版本中的文本的示例源代码

以下是完整的示例源代码，演示了如何使用 Aspose.Words for .NET 的“忽略删除修订中的文本”功能：

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//插入未修改的文本。
	builder.Writeln("Deleted");
	builder.Write("Text");

	//删除第一段并跟踪修订内容。
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

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 中的“忽略删除修订中的文本”功能。此功能对于在操作文档时忽略删除修订中的文本非常有用。我们按照分步指南创建文档、插入文本、使用修订跟踪删除段落、应用“忽略删除修订中的文本”功能以及执行查找和替换操作。

### 常见问题解答

#### 问：Aspose.Words for .NET 中的“忽略删除修订中的文本”功能是什么？

答：Aspose.Words for .NET 中的“忽略删除修订版本中的文本”功能允许您指定是否应在某些操作（例如查找和替换文本）期间忽略删除修订版本中的文本。启用此功能后，操作期间不会考虑修订版本中的已删除文本。

#### 问：Aspose.Words for .NET是什么？

答：Aspose.Words for .NET 是一个功能强大的库，用于创建、编辑 Word 文档并将其转换为 .NET 应用程序。它为文档的文字处理提供了许多高级功能，包括修订管理。

#### 问：如何在 Aspose.Words for .NET 中创建新文档？

答：在开始处理文档中的文本之前，您需要使用 Aspose.Words for .NET 创建一个新文档。这可以通过实例化`Document`对象。以下是创建新文档的示例代码：

```csharp
Document doc = new Document();
```

#### 问：如何使用 Aspose.Words for .NET 将未编辑的文本插入文档？

答：获得文档后，您可以使用`DocumentBuilder`对象。例如，要插入文本“已删除文本”，您可以使用`Writeln`和`Write`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### 问：如何在 Aspose.Words for .NET 中删除带有修订跟踪的段落？

答：为了说明“忽略删除修订中的文本”功能的使用，我们将使用修订跟踪从文档中删除一个段落。这将使我们能够看到此功能如何影响后续操作。

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### 问：如何在 Aspose.Words for .NET 中启用“忽略删除修订中的文本”功能？

答：现在我们已经准备好了文档，删除了一个段落，我们可以使用`FindReplaceOptions`对象。我们将设置`IgnoreDeleted`财产`true`：

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### 问：如何在 Aspose.Words for .NET 中使用正则表达式进行搜索和替换？

答：要对文档文本执行搜索和替换操作，我们将使用正则表达式。在我们的示例中，我们将搜索字母“e”的所有出现位置，并将其替换为星号“* “。我们将使用.NET`Regex`此类别：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### 问：如何在 Aspose.Words for .NET 中查看更改的文档内容？

答：应用搜索和替换后，我们可以使用`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

#### 问：如何在 Aspose.Words for .NET 的输出结果中包含已删除的文本？

答：如果我们想在输出结果中包含已删除的文本，我们可以更改选项以不忽略已删除的文本。为此，我们将设置`IgnoreDeleted`财产`false`：

```csharp
options. IgnoreDeleted = false;
```

#### 问：如何在 Aspose.Words for .NET 中显示已删除文本的编辑文档？

答：更改选项后，我们可以进行新的搜索和替换，以获得包含已删除文本的结果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
