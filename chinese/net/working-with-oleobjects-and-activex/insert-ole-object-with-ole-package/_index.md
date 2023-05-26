---
title: 使用 Ole 包插入 Ole 对象
linktitle: 使用 Ole 包插入 Ole 对象
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将带有 OLE 包的 OLE 对象插入到文档中。
type: docs
weight: 10
url: /zh/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

这是一个分步指南，用于解释下面的 C# 源代码，该代码说明了如何使用 Aspose.Words for .NET 插入带有 OLE 包的 OLE 对象。

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

## 步骤 3：插入带有 OLE 包的 OLE 对象
使用文档生成器`InsertOleObject`方法将带有 OLE 包的 OLE 对象插入到文档中。指定数据流、对象类型、显示选项和其他必要设置。

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## 第 4 步：保存文档
使用文档的`Save`将文档保存到文件的方法。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### 使用 Aspose.Words for .NET 插入带有 OLE 包的 OLE 对象的示例源代码

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

这是一个完整的代码示例，用于使用 Aspose.Words for .NET 插入带有 OLE 包的 OLE 对象。请务必导入必要的引用并按照前面描述的步骤将此代码集成到您的项目中。