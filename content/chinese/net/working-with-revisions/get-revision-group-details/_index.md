---
title: 获取修订组详细信息
linktitle: 获取修订组详细信息
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 在 Word 文档中获取修订组详细信息。
type: docs
weight: 10
url: /zh/net/working-with-revisions/get-revision-group-details/
---

在本分步指南中，我们将向您展示如何使用 Aspose.Words for .NET 获取 Word 文档中一组修订的详细信息。我们将为您提供完整的源代码并向您展示如何格式化 markdown 输出。

## 步骤 1：加载文档

第一步是上传包含修订内容的文档。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：浏览修订版本

接下来，我们将循环遍历文档中现有的修订并显示其详细信息，例如类型、作者、日期和修订文本。

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### 使用 Aspose.Words for .NET 获取修订组详细信息的示例源代码

以下是使用 Aspose.Words for .NET 获取文档中一组修订的详细信息的完整源代码：

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 获取 Word 文档中一组修订的详细信息。通过使用循环和适当的属性，我们能够显示修订类型、作者、日期和修订文本等详细信息。Aspose.Words for .NET 提供了许多用于操作 Word 文档的强大功能，包括修订管理。现在，您可以使用这些知识使用 Aspose.Words for .NET 将修订组详细信息放入您自己的 Word 文档中。

### 常见问题解答

#### 问：如何将修订后的文档加载到 Aspose.Words for .NET 中？

答：使用`Document` Aspose.Words for .NET 类用于从包含修订的文件中加载文档。您可以指定完整的文档路径。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### 问：如何获取 Aspose.Words for .NET 中修订组的详细信息？

答：使用循环遍历文档的修订版本，并访问每个修订版本的属性以获取所需的详细信息。您可以使用`RevisionType`, `Author`, `DateTime`和`ParentNode`属性分别获取修订类型、作者、日期和修订文本。

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### 问：如何检查修订是否属于 Aspose.Words for .NET 中的某个组？

答：使用`Group`的财产`Revision`对象来检查修订是否属于某个组。如果`Group`财产是`null`，则表示该修订不属于任何组。

```csharp
if (revision.Group != null)
{
      //修订版本属于某个组
}
else
{
      //该修订不属于任何组
}
```