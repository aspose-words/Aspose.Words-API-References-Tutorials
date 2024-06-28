---
title: 使用 Ole 包在 Word 中插入 Ole 对象
linktitle: 使用 Ole 包在 Word 中插入 Ole 对象
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将带有 OLE 包的 OLE 对象插入到文档中。
type: docs
weight: 10
url: /zh/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

下面是解释 C# 源代码的分步指南，说明如何使用 Aspose.Words for .NET 在具有 OLE 包的 Word 中插入 OLE 对象。

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

## 步骤 3：插入带有 OLE 包的 OLE 对象
使用文档生成器`InsertOleObject`方法将带有 OLE 包的 OLE 对象插入到文档中。指定数据流、对象类型、显示选项和其他必要的设置。

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

## 结论

总之，我们已经完成了使用 Aspose.Words for .NET 将 OLE 对象插入带有 OLE 包的 Word 文档的分步指南。

通过执行这些步骤，您将能够使用 Aspose.Words for .NET 将带有 OLE 包的 OLE 对象成功插入到 Word 文档中。请务必导入必要的参考并仔细按照说明进行操作，以获得所需的结果。

### 使用 ole 包在 word 中插入 ole 对象的常见问题解答

#### 问：我需要导入哪些凭据才能使用 Aspose.Words for .NET？

答：要使用 Aspose.Words for .NET，您需要导入以下引用：

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### 问：如何创建新文档和文档生成器？

答：您可以使用以下命令创建一个新文档`Document`类和文档生成器使用`DocumentBuilder`类，如下图：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### 问：如何将带有 OLE 包的 OLE 对象插入到文档中？

答：使用`InsertOleObject`文档生成器的方法（`DocumentBuilder`) 将带有 OLE 包的 OLE 对象插入到文档中。指定数据流、对象类型、显示选项和其他必要的设置。这是一个例子：

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

答：使用文档`Save`将文档保存到文件的方法。这是一个例子：

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### 问：您能否提供使用 Aspose.Words for .NET 插入带有 OLE 包的 OLE 对象的完整示例？

答：以下是使用 Aspose.Words for .NET 插入带有 OLE 包的 OLE 对象的完整示例代码。请务必导入必要的引用并按照前面描述的步骤将此代码集成到您的项目中：

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

关于使用 Aspose.Words for .NET 将带有 OLE 包的 OLE 对象插入到 Word 文档中的教程到此结束。请随意导入必要的引用并按照描述的步骤将此代码集成到您的项目中。如果您还有任何疑问，请随时与我们联系。