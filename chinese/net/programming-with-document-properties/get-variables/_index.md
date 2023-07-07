---
title: 获取变量
linktitle: 获取变量
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 检索文档变量的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-properties/get-variables/
---

在本教程中，我们将引导您完成 C# 源代码，以使用 Aspose.Words for .NET 从文档中检索变量。此功能允许您访问文档中定义的变量。

## 第 1 步：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：加载文档

在此步骤中，我们将加载要从中检索变量的 Word 文档。使用以下代码加载文档：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`与文档所在目录的实际路径。

## 第 3 步：检索变量

现在我们将检索文档中定义的变量。使用以下代码：

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

此代码迭代文档变量中的每个键值对并检索每个变量的名称和值。然后将变量连接起来以显示每个变量的信息。

### 使用 Aspose.Words for .NET 获取变量的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

请务必在中指定正确的文档路径`dataDir`多变的。

您现在已经学习了如何使用 Aspose.Words for .NET 从文档中检索变量。通过遵循本教程中提供的分步指南，您可以轻松访问和查看您自己的文档中的变量。