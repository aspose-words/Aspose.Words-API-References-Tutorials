---
title: 在 Word 文档中插入 Ole 对象作为图标
linktitle: 在 Word 文档中插入 Ole 对象作为图标
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中插入 OLE 对象作为图标。
type: docs
weight: 10
url: /zh/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

下面是解释 C# 源代码的分步指南，说明如何使用 Aspose.Words for .NET 在 Word 文档中插入 OLE 对象作为图标。

## 第 1 步：导入必要的参考文献
在开始之前，请确保您已将使用 Aspose.Words for .NET 所需的引用导入到您的项目中。这包括导入 Aspose.Words 库并将所需的命名空间添加到源文件中。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## 步骤 2：创建新文档和文档生成器
在此步骤中，我们将使用以下命令创建一个新文档`Document`类和文档生成器使用`DocumentBuilder`班级。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：插入 OLE 对象作为图标
使用文档生成器`InsertOleObjectAsIcon`方法将 OLE 对象作为图标插入到文档中。指定 OLE 文件路径、显示标志、图标路径和嵌入对象名称。

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## 步骤 4：保存文档
使用文档的`Save`将文档保存到文件的方法。

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

这是一个完整的代码示例，用于使用 Aspose.Words for .NET 将 OLE 对象作为图标插入。请务必导入必要的引用并按照前面描述的步骤将此代码集成到您的项目中。

## 结论

总之，我们探索了使用 Aspose.Words for .NET 在 Word 文档中插入 OLE 对象作为图标的分步指南。

通过执行这些步骤，您将能够使用 Aspose.Words for .NET 在 Word 文档中成功插入 OLE 对象作为图标。请务必导入必要的参考并仔细按照说明进行操作，以获得所需的结果。

### 在 Word 文档中插入 ole 对象作为图标的常见问题解答

#### 问：使用 Aspose.Words for .NET 在 Word 文档中插入 OLE 对象作为图标需要哪些引用？

答：您需要将以下引用导入到您的项目中才能使用 Aspose.Words for .NET：

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### 问：如何在 Aspose.Words for .NET 中创建新文档和文档生成器？

答：您可以使用以下命令创建一个新文档`Document`类和文档生成器使用`DocumentBuilder`班级。这是一个例子：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### 问：如何在文档中插入 OLE 对象作为图标？

 A：使用文档生成器`InsertOleObjectAsIcon`方法插入 OLE 对象作为图标。指定 OLE 文件路径、显示标志、图标路径和嵌入对象名称。这是一个例子：

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### 问：如何保存以图标形式插入的 OLE 对象的文档？

答：使用文档`Save`将文档保存到文件的方法。这是一个例子：

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```