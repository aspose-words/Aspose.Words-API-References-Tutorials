---
title: 使用流将 Ole 对象插入为图标
linktitle: 使用流将 Ole 对象插入为图标
second_title: Aspose.Words for .NET API 参考
description: 了解如何通过 Aspose.Words for .NET 使用流将 OLE 对象作为图标插入。
type: docs
weight: 10
url: /zh/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

下面是一个分步指南，用于解释下面的 C# 源代码，该代码说明了如何使用带有 Aspose.Words for .NET 的流将 OLE 对象作为图标插入。

## 第 1 步：导入必要的引用
在您开始之前，请确保您已经导入了必要的引用以将 Aspose.Words for .NET 应用到您的项目中。这包括导入 Aspose.Words 库并将所需的命名空间添加到您的源文件中。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## 第 2 步：创建新文档和文档生成器
在此步骤中，我们将使用`Document`类和文档生成器使用`DocumentBuilder`班级。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：从流中插入 OLE 对象作为图标
使用文档生成器的`InsertOleObjectAsIcon`方法将 OLE 对象作为图标从流插入到文档中。指定数据流、对象类型、图标路径和嵌入对象名称。

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## 第 4 步：保存文档
使用文档的`Save`将文档保存到文件的方法。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### 使用带有 Aspose.Words for .NET 的流将 OLE 对象作为图标插入的示例源代码

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

这是一个完整的代码示例，用于使用带有 Aspose.Words for .NET 的流将 OLE 对象作为图标插入。请务必导入必要的引用并按照前面描述的步骤将此代码集成到您的项目中。