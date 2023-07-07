---
title: 忽略插入修订内的文本
linktitle: 忽略插入修订内的文本
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 的“忽略插入修订内的文本”功能来操作 Word 文档中的插入修订。
type: docs
weight: 10
url: /zh/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的 Ignore Text Inside Insert Revisions 功能。当我们在操作文档时想要忽略插入修订中的文本时，此功能非常有用。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第 1 步：创建新文档

在我们开始操作插入修订中的文本之前，我们需要使用 Aspose.Words for .NET 创建一个新文档。这可以通过实例化一个来完成`Document`目的：

```csharp
Document doc = new Document();
```

## 第 2 步：插入带有修订跟踪的文本

一旦我们有了文档，我们就可以使用`DocumentBuilder`目的。例如，要插入带有修订跟踪的“已插入”文本，我们可以使用`StartTrackRevisions`, `Writeln`和`StopTrackRevisions`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## 第 3 步：插入未经审阅的文本

除了带有修订跟踪的文本之外，我们还可以使用`DocumentBuilder`目的。例如，要插入文本“Text”而不进行修改，我们可以使用`Write`方法：

```csharp
builder.Write("Text");
```

## 步骤 4：使用“忽略插入修订内的文本”功能

要在后续操作中忽略插入修订内的文本，我们可以使用`FindReplaceOptions`对象并设置`IgnoreInserted`财产给`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## 步骤 5：使用正则表达式进行搜索和替换

为了对文档文本执行搜索操作和替换，我们将使用正则表达式。在我们的示例中，我们将搜索所有出现的字母“e”并将其替换为星号“*“。我们将使用 .NET`Regex`为此类：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## 第6步：查看修改后的文档输出

应用搜索和替换后，我们可以使用以下命令显示文档的更改内容`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## 步骤 7：更改选项以包括插入修订

如果我们想在输出结果中包含插入修订内的文本，我们可以更改选项以不忽略插入修订。为此我们将设置`IgnoreInserted`财产给`false`:

```csharp
options.IgnoreInserted = false;
```

## 步骤 8：查看带有插入修订的修改文档

更改选项后，我们可以再次执行搜索并替换以获得包含插入修订内文本的结果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### 使用 Aspose.Words for .NET 忽略插入修订内的文本的示例源代码

以下是完整的示例源代码，演示如何使用 Aspose.Words for .NET 忽略插入修订内的文本功能：


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//插入带有跟踪修订的文本。
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	//插入未修改的文本。
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## 结论

在本文中，我们探索了 C# 源代码，以了解如何在 Aspose.Words for .NET 中使用 Ignore Text Inside Insert Revisions 功能。我们按照分步指南创建文档，插入带有跟踪修订和未修订文本的文本，使用“忽略插入修订内的文本”功能，使用正则表达式执行搜索和替换操作，并显示修改后的文档。