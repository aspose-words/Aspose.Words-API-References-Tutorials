---
title: 忽略插入修订中的文本
linktitle: 忽略插入修订中的文本
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 的“忽略插入修订中的文本”功能来操作 Word 文档中的插入修订。
type: docs
weight: 10
url: /zh/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的“忽略插入修订中的文本”功能。当我们想要在操作文档时忽略插入修订中的文本时，此功能很有用。

## 先决条件

- C# 语言的基本知识。
- 安装了 Aspose.Words 库的.NET 开发环境。

## 步骤 1：创建新文档

在开始操作插入修订中的文本之前，我们需要使用 Aspose.Words for .NET 创建一个新文档。这可以通过实例化`Document`目的：

```csharp
Document doc = new Document();
```

## 第 2 步：插入带有修订跟踪的文本

一旦我们有了文档，我们就可以使用`DocumentBuilder`对象。例如，要插入带有修订跟踪的“已插入”文本，我们可以使用`StartTrackRevisions`, `Writeln`和`StopTrackRevisions`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## 步骤 3：插入未审阅的文本

除了带有修订跟踪的文本外，我们还可以使用`DocumentBuilder`对象。例如，要插入不带修订的文本“Text”，我们可以使用`Write`方法：

```csharp
builder.Write("Text");
```

## 步骤 4：使用“忽略插入修订内容内的文本”功能

为了在后续操作中忽略插入修订中的文本，我们可以使用`FindReplaceOptions`对象并设置`IgnoreInserted`财产`true`：

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## 步骤 5：使用正则表达式进行搜索和替换

为了对文档文本执行搜索操作和替换，我们将使用正则表达式。在我们的示例中，我们将搜索字母“e”的所有出现位置，并将其替换为星号“*“我们将使用.NET 的`Regex`此类别：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## 步骤6：查看修改后的文档输出

应用搜索和替换后，我们可以使用`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## 步骤 7：更改选项以包括插入修订

如果我们想在输出结果中包含插入修订中的文本，我们可以更改选项以不忽略插入修订。为此，我们将设置`IgnoreInserted`财产`false`：

```csharp
options.IgnoreInserted = false;
```

## 步骤8：使用插入修订查看修改后的文档

更改选项后，我们可以再次执行搜索和替换以获得包含插入修订内容的文本的结果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### 使用 Aspose.Words for .NET 忽略插入修订中的文本的示例源代码

以下是完整的示例源代码，演示了如何使用 Aspose.Words for .NET 中的“忽略插入修订版本中的文本”功能：


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

在本文中，我们探索了 C# 源代码，以了解如何在 Aspose.Words for .NET 中使用“忽略插入修订中的文本”功能。我们按照分步指南创建文档，插入带有跟踪修订和未修订文本的文本，使用“忽略插入修订中的文本”功能，使用正则表达式执行搜索和替换操作，并显示修改后的文档。

### 常见问题解答

#### 问：Aspose.Words for .NET 中的“忽略插入修订版中的文本”功能是什么？

答：Aspose.Words for .NET 中的“忽略插入修订中的文本”功能允许您指定是否应在某些操作（例如查找和替换文本）期间忽略插入修订中的文本。启用此功能后，操作期间不会考虑插入修订中的文本。

#### 问：如何使用 Aspose.Words for .NET 创建新文档？

答：要使用 Aspose.Words for .NET 创建新文档，您可以实例化一个`Document`对象。以下是创建新文档的 C# 代码示例：

```csharp
Document doc = new Document();
```

#### 问：如何在 Aspose.Words for .NET 中插入带有修订跟踪的文本？

答：一旦您有了文档，您就可以使用`DocumentBuilder`对象。例如，要插入带有修订跟踪的“已插入”文本，您可以使用`StartTrackRevisions`, `Writeln`， 和`StopTrackRevisions`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### 问：如何在 Aspose.Words for .NET 中插入未修改的文本？

答：除了带有修订跟踪的文本外，您还可以使用`DocumentBuilder`对象。例如，要插入不带修订的文本“Text”，您可以使用`Write`方法：

```csharp
builder.Write("Text");
```

#### 问：如何在 Aspose.Words for .NET 中忽略插入修订版中的文本？

答：要在后续操作中忽略插入修订中的文本，可以使用`FindReplaceOptions`对象并设置`IgnoreInserted`财产`true`：

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### 问：如何在 Aspose.Words for .NET 中使用正则表达式执行搜索和替换？

答：要使用正则表达式对文档文本执行搜索和替换操作，可以使用.NET`Regex`类。例如，搜索所有出现的字母“e”并将其替换为星号“* "，您可以创建一个`Regex`对象并将其与`Replace`方法：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### 问：如何在 Aspose.Words for .NET 中查看文档的修改输出？

答：应用搜索和替换操作后，您可以使用`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

#### 问：如何在 Aspose.Words for .NET 的输出结果中包含插入修订？

答：要将插入修订内的文本包含在输出结果中，您可以更改选项以不忽略插入修订。为此，您可以设置`IgnoreInserted`的财产`FindReplaceOptions`反对`false`：

```csharp
options.IgnoreInserted = false;
```

#### 问：如何在 Aspose.Words for .NET 中显示插入修订版的修改后的文档？

答：将选项更改为包含插入修订后，您可以再次执行搜索和替换以获得包含插入修订内的文本的结果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```