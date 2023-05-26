---
title: 检测带空格的编号
linktitle: 检测带空格的编号
second_title: Aspose.Words for .NET API 参考
description: 了解如何在 Aspose.Words for .NET 中检测带有空格的列表编号。轻松改善文档结构。
type: docs
weight: 10
url: /zh/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
在本教程中，我们将探索为 Aspose.Words for .NET 的“检测带空格的编号”功能提供的 C# 源代码。此功能允许您从包含列表编号后跟空格的文本文档中检测和创建列表。

## 第 1 步：设置环境

在您开始之前，请确保您已经使用 Aspose.Words for .NET 设置了您的开发环境。确保您已经添加了必要的引用并导入了适当的命名空间。

## 第 2 步：创建文本文档

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

在此步骤中，我们创建一个文本字符串来模拟包含列表编号后跟空格的文本文档。我们使用不同的列表分隔符，例如句点、右括号、项目符号和空格。

## 第 3 步：配置上传选项

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

在此步骤中，我们配置文档加载选项。我们创造一个新的`TxtLoadOptions`对象并设置`DetectNumberingWithWhitespaces`财产给`true`.这将允许 Aspose.Words 检测列表编号，即使它们后面是空格。

## 第 4 步：加载文档并保存

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

在此步骤中，我们使用指定的文本字符串和加载选项加载文档。我们使用一个`MemoryStream`将文本字符串转换为内存流。然后我们将生成的文档保存为 .docx 格式。

### 使用 Aspose.Words for .NET 的空白编号检测功能的示例源代码。

```csharp

            
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
//创建一个字符串形式的明文文档，其中的部分可以解释为列表。
//加载后，前三个列表将始终被 Aspose.Words 检测到，
//并在加载后为它们创建 List 对象。
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

//第四个列表，列表编号和列表项内容之间有空格，
//只有当 LoadOptions 对象中的“DetectNumberingWithWhitespaces”设置为 true 时，才会被检测为列表，
//避免以数字开头的段落被错误地检测为列表。
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

//在将 LoadOptions 作为参数应用时加载文档并验证结果。
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

现在您可以运行源代码来加载包含带有空格的列表编号的文本文档，然后创建一个包含检测到的列表的 .docx 文档。输出文件将保存在指定目录中，名称为“WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx”。

## 结论
在本教程中，我们探讨了 Aspose.Words for .NET 中的空格编号检测功能。我们学习了如何从包含列表编号后跟空格的文本文档创建列表。

此功能对于处理包含以不同方式格式化的列表编号的文档非常有用。通过使用适当的加载选项，Aspose.Words 能够检测到这些列表编号，即使它们后面有空格，并将它们转换为最终文档中的结构化列表。

使用此功能可以节省您的时间并提高您的工作流程效率。您可以轻松地从文本文档中提取信息，并将它们转换为具有适当列表的结构良好的文档。

记住要考虑加载选项，例如配置空白拨号检测，以获得预期的结果。

Aspose.Words for .NET 提供了许多用于文档操作和生成的高级功能。通过进一步探索 Aspose.Words 提供的文档和示例，您将能够充分利用这个强大的库的功能。

因此，请毫不犹豫地将空格编号检测集成到您的 Aspose.Words for .NET 项目中，并利用其优势创建结构良好且可读性强的文档。


