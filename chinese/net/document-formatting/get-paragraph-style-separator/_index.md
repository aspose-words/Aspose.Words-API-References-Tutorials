---
title: 获取段落样式分隔符
linktitle: 获取段落样式分隔符
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 获取段落样式分隔符。
type: docs
weight: 10
url: /zh/net/document-formatting/get-paragraph-style-separator/
---

在本教程中，我们将引导您了解如何通过 Aspose.Words for .NET 使用“获取段落样式分隔符”功能。请按照以下步骤了解源代码并应用更改。

## 第 1 步：加载文档

首先，指定文档的目录并将文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## 第 2 步：查找段落样式分隔符

我们现在将循环遍历文档中的所有段落并检查段落是否是样式分隔符。就是这样：

```csharp
foreach(Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (paragraph.BreakIsStyleSeparator)
     {
         Console.WriteLine("Separator found!");
     }
}
```

### 使用 Aspose.Words for .NET 获取段落样式分隔符的示例源代码

以下是 Aspose.Words for .NET 的获取段落样式分隔符功能的完整源代码：

```csharp

            Document doc = new Document(MyDir + "Document.docx");

            foreach (Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
            {
                if (paragraph.BreakIsStyleSeparator)
                {
                    Console.WriteLine("Separator Found!");
                }
            }
        
```

通过此代码，您将能够使用 Aspose.Words for .NET 在文档中查找段落样式分隔符。

