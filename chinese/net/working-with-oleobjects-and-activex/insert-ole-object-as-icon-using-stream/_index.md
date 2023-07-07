---
title: 使用流将 Ole 对象插入为图标
linktitle: 使用流将 Ole 对象插入为图标
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 的流将 OLE 对象作为图标插入。
type: docs
weight: 10
url: /zh/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

下面是解释 C# 源代码的分步指南，说明了如何使用 Aspose.Words for .NET 的流将 OLE 对象作为图标插入。

## 第 1 步：导入必要的参考文献
在开始之前，请确保您已将使用 Aspose.Words for .NET 所需的引用导入到您的项目中。这包括导入 Aspose.Words 库并将所需的命名空间添加到源文件中。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## 步骤 2：创建新文档和文档生成器
在此步骤中，我们将使用以下命令创建一个新文档`Document`类和文档生成器使用`DocumentBuilder`班级。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：从流中插入 OLE 对象作为图标
使用文档生成器`InsertOleObjectAsIcon`方法将 OLE 对象作为图标从流插入到文档中。指定数据流、对象类型、图标路径和嵌入对象名称。

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## 步骤 4：保存文档
使用文档的`Save`将文档保存到文件的方法。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### 使用 Aspose.Words for .NET 的流插入 OLE 对象作为图标的示例源代码

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

这是一个完整的代码示例，用于使用 Aspose.Words for .NET 的流将 OLE 对象作为图标插入。请务必导入必要的引用并按照前面描述的步骤将此代码集成到您的项目中。

## 结论

上面的分步指南解释了如何使用 Aspose.Words for .NET 的流程在 Word 文档中插入 OLE 对象作为图标。通过执行所描述的步骤，您将能够将此功能集成到您的项目中。请务必导入必要的引用，创建新文档和文档生成器，从流中将 OLE 对象作为图标插入，然后保存文档。使用提供的示例代码作为起点，并根据您的需求进行自定义。

### 常见问题解答

#### 问：如何导入必要的引用以使用 Aspose.Words for .NET？

A. 要导入必要的参考，您必须执行以下步骤：

添加以下内容`using`源文件顶部的语句：

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
确保您已将 Aspose.Words 库添加到您的项目中。

#### 问：如何使用 Aspose.Words for .NET 创建新文档和文档生成器？

A. 要创建新文档和文档生成器，您可以按照以下步骤操作：

使用`Document`类来创建新文档：

```csharp
Document doc = new Document();
```
使用`DocumentBuilder`类来创建与先前创建的文档关联的文档构建器：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### 问：如何使用 Aspose.Words for .NET 从流中插入 OLE 对象作为图标？

A. 要从流中插入 OLE 对象作为图标，可以按照以下步骤操作：

使用`InsertOleObjectAsIcon`文档生成器插入 OLE 对象的方法：

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### 问：如何将文档保存到文件中？

A. 要将文档保存到文件中，您可以使用`Save`指定目标路径的文档方法：

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### 问：如何将用于将 OLE 对象作为图标从流插入到我的项目中的代码嵌入到我的项目中？

A. 要将用于将 OLE 对象作为图标从流插入项目的代码嵌入到您的项目中，请执行以下步骤：
- 通过添加适当的内容来导入必要的参考文献`using`声明。
- 使用以下命令创建一个新文档和文档生成器`Document`和`DocumentBuilder`类。
- 使用代码将 OLE 对象作为图标从流中插入。
- 使用保存文档`Save`方法与适当的目标路径。

通过执行这些步骤，您将能够使用 Aspose.Words for .NET 从流中成功插入 OLE 对象作为图标。请务必按照说明进行操作并导入必要的参考文献以获得所需的结果。