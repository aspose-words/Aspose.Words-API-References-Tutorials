---
title: 附加导入格式选项
linktitle: 附加导入格式选项
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 使用导入格式选项附加文档。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/append-with-import-format-options/
---

本教程解释了如何使用 Aspose.Words for .NET 通过导入格式选项将一个文档的内容附加到另一个文档。提供的源代码演示了如何打开源文档和目标文档、指定导入格式选项以及将源文档附加到目标文档。

## 第 1 步：设置项目

确保您具有以下先决条件：

- 安装了 Aspose.Words for .NET 库。您可以从 Aspose 官方网站下载或使用 NuGet 包管理器安装它。
- 源文档和目标文档所在的文档目录路径。

## 第 2 步：打开源文档和目标文档

使用打开源文档和目标文档`Document`类构造函数。代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 第 3 步：指定导入格式选项

创建一个实例`ImportFormatOptions`类来指定导入格式选项。在这个例子中，我们使用`KeepSourceNumbering`属性以确保在与目标文档发生冲突时使用源文档中的编号。

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## 第 4 步：将源文档附加到目标文档

使用`AppendDocument`附加源文档的目标文档的方法。经过`ImportFormatMode.UseDestinationStyles`作为第二个参数使用目标文档的样式和格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## 第 5 步：保存目标文档

最后，使用保存修改后的目标文档`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

这样就完成了使用 Aspose.Words for .NET 附加带有导入格式选项的文档的实现。

### 使用 Aspose.Words for .NET 的 Append With Import Format Options 示例源代码 

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