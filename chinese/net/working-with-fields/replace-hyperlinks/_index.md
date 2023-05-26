---
title: 替换超链接
linktitle: 替换超链接
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 替换 Word 文档中的超链接。替换超链接的分步说明。
type: docs
weight: 10
url: /zh/net/working-with-fields/replace-hyperlinks/
---

这是一个分步指南，用于解释以下 C# 源代码以使用 Aspose.Words for .NET 功能替换超链接。在使用此代码之前，请确保您已将 Aspose.Words 库包含在您的项目中。

## 第一步：设置文档目录路径

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

请务必指定包含以下内容的文档目录的正确路径`Hyperlinks.docx`文件。

## 第 2 步：加载包含超链接的文档

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

在这里，我们正在创建一个实例`Document`来自指定文件的类。

## 第 3 步：浏览字段以查找超链接

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         //一些超链接可能是本地的（链接到文档内部的书签），我们忽略它们。
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

此循环遍历文档中的所有字段以查找类型的字段`FieldType.FieldHyperlink`.一旦找到这种类型的字段，我们通过检查`SubAddress`财产。如果不是，我们将链接地址替换为`"http://www.aspose.com"`结果是`"Aspose - The .NET & Java Component Editor"`.

## 第 4 步：保存修改后的文档

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

最后，我们将修改后的文档和替换后的超链接保存到指定的文件中。

### 用 Aspose.Words for .NET 替换超链接的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         //一些超链接可能是本地的（链接到文档内部的书签），我们忽略它们。
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

这是使用 Aspose.Words for .NET 替换文档中超链接的示例源代码。