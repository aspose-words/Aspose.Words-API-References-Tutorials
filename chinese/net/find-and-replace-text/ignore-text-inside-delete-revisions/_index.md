---
title: 忽略删除修订中的文本
linktitle: 忽略删除修订中的文本
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 的“忽略删除修订中的文本”功能。
type: docs
weight: 10
url: /zh/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的“忽略删除修订中的文本”功能。当我们在处理文档时想要忽略删除修订中的文本时，此功能很有用。

## Aspose.Words for .NET 库概述

在深入代码细节之前，让我简要介绍一下 Aspose.Words for .NET 库。它是一个强大的库，允许在 .NET 应用程序中创建、修改和转换 Word 文档。它提供了许多用于处理文档的高级功能，包括修订管理。

## 了解“忽略删除修订中的文本”功能

Aspose.Words for .NET 中的“忽略删除修订内的文本”功能允许您指定在某些操作（例如查找和替换文本）期间是否应忽略删除修订内的文本。启用此功能后，在操作期间不考虑修订内删除的文本。

## 第 1 步：使用 Aspose.Words for .NET 创建新文档

在开始操作文档中的文本之前，我们需要使用 Aspose.Words for .NET 创建一个新文档。它可以通过实例化一个`Document`目的：

```csharp
Document doc = new Document();
```

## 第 2 步：将未修订的文本插入文档

一旦我们有了文档，我们就可以使用`DocumentBuilder`目的。例如，要插入文本“Deleted Text”，我们可以使用`Writeln`和`Write`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## 第 3 步：删除带有跟踪修订的段落

为了说明“忽略删除修订中的文本”功能的使用，我们将使用修订跟踪从文档中删除一个段落。这将使我们能够看到此功能如何影响后续操作。

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## 第 4 步：应用“忽略删除修订中的文本”功能

现在我们已经通过删除段落准备了文档，我们可以使用`FindReplaceOptions`目的。我们将设置`IgnoreDeleted`财产给`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## 第 5 步：使用正则表达式进行查找和替换

要对文档的文本执行搜索和替换操作，我们将使用正则表达式。在我们的示例中，我们将搜索所有出现的字母“e”并将它们替换为星号“* “。 。网`Regex`类用于此：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## 第 6 步：显示修改后的文档输出

应用搜索和替换后，我们可以使用`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## 第 7 步：修改选项以包含已删除的文本

如果我们想在输出结果中包含删除的文本，我们可以将选项更改为不忽略删除的文本。为此，我们将设置`IgnoreDeleted`财产给`false`:

```csharp
options. IgnoreDeleted = false;
```

## 第 8 步：输出修改后的文档和删除的文本

更改选项后，我们可以再次执行搜索和替换以获得包含已删除文本的结果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### 使用 Aspose.Words for .NET 忽略删除修订中的文本的示例源代码

下面是完整的示例源代码，用于演示如何使用 Aspose.Words for .NET 的“忽略删除修订中的文本”功能：

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//插入未修订的文本。
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

在本文中，我们研究了 C# 源代码以了解如何在 Aspose.Words for .NET 中使用“忽略删除修订中的文本”功能。此功能对于在操作文档时忽略删除修订中的文本很有用。我们按照分步指南创建文档、插入文本、删除带有修订跟踪的段落、应用“忽略删除修订中的文本”功能以及执行查找和替换操作。

