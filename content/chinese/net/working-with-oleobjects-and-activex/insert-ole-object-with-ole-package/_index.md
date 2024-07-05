---
title: 使用 Ole 包在 Word 中插入 Ole 对象
linktitle: 使用 Ole 包在 Word 中插入 Ole 对象
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将带有 OLE 包的 OLE 对象插入文档。
type: docs
weight: 10
url: /zh/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

下面是一步一步的指南，解释下面的 C# 源代码，说明如何使用 Aspose.Words for .NET 使用 OLE 包在 Word 中插入 OLE 对象。

## 步骤 1：导入必要的参考资料
开始之前，请确保已将使用 Aspose.Words for .NET 所需的引用导入到项目中。这包括导入 Aspose.Words 库并将所需的命名空间添加到源文件中。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## 第 2 步：创建新文档和文档生成器
在此步骤中，我们将使用`Document`类和使用文档生成器`DocumentBuilder`班级。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：插入带有 OLE 包的 OLE 对象
使用文档生成器的`InsertOleObject`方法将带有 OLE 包的 OLE 对象插入文档。指定数据流、对象类型、显示选项和其他必要的设置。

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

## 步骤 4：保存文档
使用文档的`Save`方法将文档保存到文件。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### 使用 Aspose.Words for .NET 的 OLE 包插入 OLE 对象的示例源代码

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

这是使用 Aspose.Words for .NET 的 OLE 包插入 OLE 对象的完整代码示例。请确保导入必要的引用并按照前面描述的步骤将此代码集成到您的项目中。

## 结论

总之，我们已经完成了一步一步的指南，使用 Aspose.Words for .NET 将 OLE 对象插入到带有 OLE 包的 Word 文档中。

通过遵循这些步骤，您将能够使用 Aspose.Words for .NET 将带有 OLE 包的 OLE 对象成功插入到 Word 文档中。请务必导入必要的引用并仔细遵循说明以获得所需的结果。

### 使用 ole 包在 Word 中插入 ole 对象的常见问题解答

#### 问：我需要导入哪些凭证才能使用 Aspose.Words for .NET？

答：要使用 Aspose.Words for .NET，您需要导入以下参考：

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### 问：如何创建新文档和文档生成器？

答：您可以使用`Document`类和使用文档生成器`DocumentBuilder`类，如下图所示：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### 问：如何将带有 OLE 包的 OLE 对象插入到文档中？

答：使用`InsertOleObject`文档生成器的方法（`DocumentBuilder`) 将带有 OLE 包的 OLE 对象插入文档。指定数据流、对象类型、显示选项和其他必要的设置。以下是示例：

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### 问：如何保存文档？

答：使用文档`Save`方法将文档保存到文件。以下是示例：

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### 问：您能提供使用 Aspose.Words for .NET 的 OLE 包插入 OLE 对象的完整示例吗？

答：这是使用 Aspose.Words for .NET 插入带有 OLE 包的 OLE 对象的完整示例代码。请确保导入必要的引用并按照前面描述的步骤将此代码集成到您的项目中：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

至此，我们完成了使用 Aspose.Words for .NET 将带有 OLE 包的 OLE 对象插入 Word 文档的教程。请随意导入必要的引用并按照所述步骤将此代码集成到您的项目中。如果您有任何其他问题，请随时与我们联系。