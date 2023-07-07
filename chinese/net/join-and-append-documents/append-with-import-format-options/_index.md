---
title: 添加导入格式选项
linktitle: 添加导入格式选项
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 附加具有导入格式选项的文档。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/append-with-import-format-options/
---

本教程介绍如何使用 Aspose.Words for .NET 通过导入格式选项将一个文档的内容附加到另一个文档。提供的源代码演示了如何打开源文档和目标文档、指定导入格式选项以及将源文档附加到目标文档。

## 第 1 步：设置项目

确保您具备以下先决条件：

- 已安装 Aspose.Words for .NET 库。您可以从 Aspose 官方网站下载它或使用 NuGet 包管理器来安装它。
- 源文档和目标文档所在的文档目录路径。

## 步骤 2：打开源文档和目标文档

使用以下命令打开源文档和目标文档`Document`类构造函数。代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 步骤 3：指定导入格式选项

创建一个实例`ImportFormatOptions`类来指定导入格式选项。在这个例子中，我们使用`KeepSourceNumbering`属性，以确保在与目标文档发生冲突时使用源文档的编号。

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## 步骤 4：将源文档附加到目标文档

使用`AppendDocument`目标文档附加源文档的方法。经过`ImportFormatMode.UseDestinationStyles`作为第二个参数来使用目标文档的样式和格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## 步骤 5：保存目标文档

最后，使用以下命令保存修改后的目标文档`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

这样就完成了使用 Aspose.Words for .NET 附加具有导入格式选项的文档的实现。

### 使用 Aspose.Words for .NET 附加导入格式选项的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//指定如果源文档和目标文档中的编号冲突，
	//然后将使用源文档中的编号。
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```