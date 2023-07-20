---
title: 忽略字段内的文本
linktitle: 忽略字段内的文本
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 的“忽略字段内的文本”功能。
type: docs
weight: 10
url: /zh/net/find-and-replace-text/ignore-text-inside-fields/
---
在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的 Ignore Text Inside Fields 功能。当我们在操作文档时想要忽略字段内的文本时，此功能非常有用。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第 1 步：创建新文档

在开始操作字段内的文本之前，我们需要使用 Aspose.Words for .NET 创建一个新文档。这可以通过实例化一个来完成`Document`目的：

```csharp
Document doc = new Document();
```

## 第 2 步：插入一个包含文本的字段

一旦我们有了一个文档，我们就可以使用 a 在其中插入一个包含文本的字段`DocumentBuilder`目的。例如，要插入带有文本“字段中的文本”的“INCLUDETEXT”字段，我们可以使用`InsertField`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## 步骤 3：使用“忽略字段内的文本”功能

要在后续操作中忽略字段内的文本，我们可以使用`FindReplaceOptions`对象并设置`IgnoreFields`财产给`true`：

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## 步骤 4：使用正则表达式进行搜索和替换

为了对文档文本执行搜索和替换操作，我们将使用正则表达式。在我们的示例中，我们将搜索所有出现的字母“e”并将其替换为星号“*“。我们将使用 .NET`Regex`为此类：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## 第5步：查看修改后的文档输出

应用搜索和替换后，我们可以使用以下命令显示文档的更改内容`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## 第 6 步：更改选项以包含字段

我们在输出结果中包含字段内的文本，我们可以更改选项以不忽略字段。为此我们将设置`IgnoreFields`财产给`false`：

```csharp
options.IgnoreFields = false;
```

## 步骤 7：显示修改后的文档及其字段

更改选项后，我们可以再次执行搜索并替换以获得包含字段中文本的结果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### 使用 Aspose.Words for .NET 忽略字段内文本的示例源代码

以下是完整的示例源代码，演示如何使用 Aspose.Words for .NET 忽略字段内的文本功能：

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//插入带有文本的字段。
	builder.InsertField("INCLUDETEXT", "Text in field");
	
	FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
	
	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreFields = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
  
```

## 结论

在本文中，我们探索了 C# 源代码，以了解如何在 Aspose.Words for .NET 中使用“忽略字段内的文本”功能。我们按照分步指南创建一个文档，插入一个内部有文本的字段，使用“忽略字段内的文本”功能，使用正则表达式执行搜索和替换操作，并显示修改后的文档。

### 常见问题解答

#### 问：Aspose.Words for .NET 中的“忽略字段内的文本”功能是什么？

答：Aspose.Words for .NET 中的“忽略字段内的文本”功能允许您指定在某些操作（例如查找和替换文本）期间是否应忽略字段内的文本。启用此功能后，操作期间不会考虑字段内的文本。

#### 问：如何使用 Aspose.Words for .NET 创建新文档？

答：要使用 Aspose.Words for .NET 创建新文档，您可以实例化一个`Document`目的。以下是创建新文档的 C# 代码示例：

```csharp
Document doc = new Document();
```

#### 问：如何使用 Aspose.Words for .NET 在文档中插入带有文本的字段？

答：一旦有了文档，您就可以使用`DocumentBuilder`目的。例如，要插入包含文本“字段中的文本”的“INCLUDETEXT”字段，您可以使用`InsertField`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

#### 问：如何忽略 Aspose.Words for .NET 中字段内的文本？

答：要在后续操作中忽略字段内的文本，您可以使用`FindReplaceOptions`对象并设置`IgnoreFields`财产给`true`：

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

#### 问：如何在 Aspose.Words for .NET 中使用正则表达式执行搜索和替换？

答：要使用正则表达式对文档文本执行搜索和替换操作，可以使用.NET`Regex`班级。例如，要搜索所有出现的字母“e”并将其替换为星号“* “，您可以创建一个`Regex`对象并将其与`Replace`方法：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### 问：如何在 Aspose.Words for .NET 中查看文档的修改输出？

 A：应用搜索和替换操作后，您可以使用以下命令查看文档的更改内容：`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

#### 问：如何在 Aspose.Words for .NET 的输出结果中包含字段？

答：要在输出结果中包含字段内的文本，您可以更改选项以不忽略字段。为此，您可以设置`IgnoreFields`的财产`FindReplaceOptions`反对`false`：

```csharp
options.IgnoreFields = false;
```

#### 问：如何在 Aspose.Words for .NET 中显示修改后的文档及其字段？

答：将选项更改为包含字段后，您可以再次执行搜索并替换以获得包含字段内文本的结果：

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```