---
title: 在 Word 文档中将 Ole 对象作为图标插入
linktitle: 在 Word 文档中将 Ole 对象作为图标插入
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将 OLE 对象作为图标插入到 Word 文档中。
type: docs
weight: 10
url: /zh/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

下面是一步一步的指南，解释下面的 C# 源代码，说明如何使用 Aspose.Words for .NET 将 OLE 对象作为图标插入到 Word 文档中。

## 步骤 1：导入必要的参考资料
开始之前，请确保已将使用 Aspose.Words for .NET 所需的引用导入到项目中。这包括导入 Aspose.Words 库并将所需的命名空间添加到源文件中。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## 第 2 步：创建新文档和文档生成器
在此步骤中，我们将使用`Document`类和使用文档生成器`DocumentBuilder`班级。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：将 OLE 对象作为图标插入
使用文档生成器的`InsertOleObjectAsIcon`方法将 OLE 对象作为图标插入到文档中。指定 OLE 文件路径、显示标志、图标路径和嵌入对象名称。

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## 步骤 4：保存文档
使用文档的`Save`方法将文档保存到文件。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### 使用 Aspose.Words for .NET 将 OLE 对象作为图标插入的示例源代码

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

这是使用 Aspose.Words for .NET 将 OLE 对象作为图标插入的完整代码示例。请确保导入必要的引用并按照前面描述的步骤将此代码集成到您的项目中。

## 结论

总之，我们探索了使用 Aspose.Words for .NET 将 OLE 对象作为图标插入 Word 文档中的分步指南。

通过遵循这些步骤，您将能够使用 Aspose.Words for .NET 成功地将 OLE 对象作为图标插入到 Word 文档中。请务必导入必要的引用并仔细遵循说明以获得所需的结果。

### 在 Word 文档中将 OLE 对象作为图标插入的常见问题解答

#### 问：使用 Aspose.Words for .NET 将 OLE 对象作为图标插入到 Word 文档中需要哪些参考？

答：您需要将以下参考资料导入到您的项目中才能使用 Aspose.Words for .NET：

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### 问：如何在 Aspose.Words for .NET 中创建新文档和文档生成器？

答：您可以使用`Document`类和使用文档生成器`DocumentBuilder`类。下面是一个例子：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### 问：如何将 OLE 对象作为图标插入到文档中？

答：使用文档生成器的`InsertOleObjectAsIcon`方法将 OLE 对象插入为图标。指定 OLE 文件路径、显示标志、图标路径和嵌入对象名称。以下是示例：

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### 问：如何保存以图标形式插入的 OLE 对象文档？

答：使用文档`Save`方法将文档保存到文件。以下是示例：

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```