---
title: 现场显示结果
linktitle: 现场显示结果
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 在 Word 文档中显示字段结果的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fields/field-display-results/
---

下面是解释 C# 源代码的分步指南，该源代码使用 Aspose.Words for .NET 的“显示字段结果”功能。确保仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为文档目录的相应路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载文档

第一步是加载要在其中显示字段结果的文档。

```csharp
Document document = new Document(dataDir + "Miscellaneous fields.docx");
```

请务必将“Miscellaneous Fields.docx”替换为您自己的文件名。

## 第 3 步：更新字段

我们使用`UpdateFields()`更新文档中所有字段的方法。

```csharp
document. UpdateFields();
```

此步骤很重要，因为它可以确保正确显示字段结果。

## 第 4 步：显示现场结果

我们使用一个`foreach`循环遍历文档中的所有字段并显示其结果。

```csharp
foreach(Field field in document.Range.Fields)
     Console.WriteLine(field.DisplayResult);
```

在循环的每次迭代中，我们访问`DisplayResult`字段的属性来获取显示的结果。

### 使用 Aspose.Words for .NET 显示字段结果的源代码示例

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档。
Document document = new Document(dataDir + "Miscellaneous fields.docx");

//更新字段。
document. UpdateFields();

//显示现场结果。
foreach(Field field in document.Range.Fields)
     Console.WriteLine(field.DisplayResult);
```

在此示例中，我们上传了一个文档，更新了所有字段，然后循环显示各个字段以显示其结果。您可以使用自己的逻辑自定义此步骤来处理字段结果。

我们关于使用 Aspose.Words for .NET 的“显示字段结果”功能的指南到此结束。

### 常见问题解答

#### 问：Aspose.Words 中的结果显示字段是什么？

答：Aspose.Words 中的结果显示字段是一种在 Word 文档中显示运算或计算结果的字段。例如，结果显示字段可用于显示几个值的总和或数学公式的结果。

#### 问：如何使用Aspose.Words更新Word文档中的结果显示字段？

答：要使用Aspose.Words更新Word文档中的结果显示字段，您可以使用UpdateFields方法。该方法循环遍历文档并更新所有字段，包括结果显示字段，根据当前数据重新计算值。

#### 问：结果显示字段显示的结果可以格式化吗？

答：是的，您可以使用适当的语法来指定结果显示字段显示的结果的格式来指定格式。例如，您可以设置具有特定小数位数的数字格式或使用自定义日期格式。

#### 问：如何使用 Aspose.Words 从 Word 文档中删除结果显示字段？

答：要使用Aspose.Words从Word文档中删除结果显示字段，您可以使用Remove方法。此方法删除该字段并将其替换为其静态结果。