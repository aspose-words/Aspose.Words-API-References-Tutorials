---
title: 在 Word 文档中插入 Ole 对象
linktitle: 在 Word 文档中插入 Ole 对象
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中插入 OLE 对象。
type: docs
weight: 10
url: /zh/net/working-with-oleobjects-and-activex/insert-ole-object/
---

下面是解释 C# 源代码的分步指南，说明了如何使用 Aspose.Words for .NET 在 Word 文档中插入 OLE 对象。

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

## 步骤 3：插入 OLE 对象
使用文档生成器`InsertOleObject`方法将 OLE 对象插入到文档中。指定 OLE 对象 URL、对象类型、显示选项和其他必要的设置。

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

## 步骤 4：保存文档
使用文档的`Save`将文档保存到文件的方法。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### 使用 Aspose.Words for .NET 插入 OLE 对象的示例源代码

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

这是使用 Aspose.Words for .NET 插入 OLE 对象的完整代码示例。请务必导入必要的引用并按照前面描述的步骤将此代码集成到您的项目中。

## 结论

总之，将 OLE 对象插入 Word 文档是 Aspose.Words for .NET 提供的一项强大功能。使用此库，您可以轻松地将 OLE 对象（例如 HTML 文件、Excel 电子表格、PowerPoint 演示文稿等）嵌入到 Word 文档中。

在本文中，我们通过分步指南解释了 C# 源代码，说明了如何将 OLE 对象插入到 Word 文档中。我们介绍了必要的参考、创建新文档和文档生成器，以及插入 OLE 对象和保存文档的步骤。

### 将 OLE 对象插入 Word 文档的常见问题解答

#### 问：我需要导入哪些凭据才能使用 Aspose.Words for .NET？

答：要使用 Aspose.Words for .NET，您需要导入以下引用：

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### 问：如何创建新文档和文档生成器？

答：您可以使用以下命令创建一个新文档`Document`类和文档生成器使用`DocumentBuilder`类，如下图：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### 问：如何在文档中插入OLE对象？

答：使用`InsertOleObject`文档生成器的方法（`DocumentBuilder`) 将 OLE 对象插入到文档中。指定 OLE 对象 URL、对象类型、显示选项和其他必要的设置。这是一个例子：

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

#### 问：如何保存文档？

答：使用文档`Save`将文档保存到文件的方法。这是一个例子：

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### 问：您能否提供使用 Aspose.Words for .NET 插入 OLE 对象的完整示例？

答：这里是使用 Aspose.Words for .NET 插入 OLE 对象的完整示例代码。请务必导入必要的引用并按照前面描述的步骤将此代码集成到您的项目中：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
