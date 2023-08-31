---
title: 访问并验证 Word 文档中的签名
linktitle: 访问并验证 Word 文档中的签名
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 访问和验证 Word 文档中的数字签名。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/access-and-verify-signature/
---
在本教程中，我们将指导您完成使用 Aspose.Words for .NET 的访问和签名验证功能的步骤。此功能允许您访问 Word 文档中的数字签名并验证其有效性。请按照以下步骤操作：

## 第 1 步：加载文档并访问签名

首先上传包含数字签名的文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## 第 2 步：浏览数字签名

使用循环遍历文档中的所有数字签名：

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	//访问签名信息
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	//此属性仅在 MS Word 文档中可用。
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

请务必根据您的需要自定义显示消息。

### 使用 Aspose.Words for .NET 访问和验证签名的示例源代码

以下是使用 Aspose.Words for .NET 进行访问和签名验证的完整源代码：

```csharp
	
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		//此属性仅在 MS Word 文档中可用。
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

通过执行这些步骤，您将能够使用 Aspose.Words for .NET 轻松访问和验证 Word 文档中的数字签名。

## 结论

在本教程中，我们探索了使用 Aspose.Words for .NET 访问和验证 Word 文档中的数字签名的功能。通过按照提供的步骤操作，您可以轻松加载文档、访问其数字签名并验证其有效性。访问和验证数字签名的能力提供了一种确保 Word 文档的完整性和真实性的方法。 Aspose.Words for .NET 提供了强大的 API，用于带有数字签名的文字处理，使您能够自动化验证过程并增强文档的安全性。

### 常见问题解答

#### 问：Word 文档中的数字签名是什么？

答：Word 文档中的数字签名是提供一种验证文档完整性和来源的方法的电子签名。它们是使用数字证书和加密算法创建的，允许收件人验证文档是否未被更改并且来自可信来源。

#### 问：如何使用 Aspose.Words for .NET 访问 Word 文档中的数字签名？

答：要使用 Aspose.Words for .NET 访问 Word 文档中的数字签名，您可以按照以下步骤操作：
1. 使用加载文档`Document`类并指定文档文件的路径。
2. 使用循环来迭代`DigitalSignatures`文档的集合。每次迭代都代表一个数字签名。

#### 问：我可以从 Word 文档中的数字签名访问哪些信息？

答：通过 Word 文档中的数字签名，您可以访问各种信息，例如：
- 有效性：检查签名是否有效。
- 注释：获取签名者指定的签名原因。
- 签名时间：获取文档签名的时间。
- 主题名称：检索签名者或证书主题的名称。
- 颁发者名称：获取证书颁发者的名称。

#### 问：我可以使用 Aspose.Words for .NET 验证 Word 文档中数字签名的有效性吗？

答：是的，您可以使用 Aspose.Words for .NET 验证 Word 文档中数字签名的有效性。通过访问`IsValid`的财产`DigitalSignature`对象，您可以确定签名是否有效。

#### 问：如何使用 Aspose.Words for .NET 验证 Word 文档中数字签名的有效性？

答：要使用 Aspose.Words for .NET 验证 Word 文档中数字签名的有效性，您可以按照以下步骤操作：
1. 访问`DigitalSignatures`文档的集合。
2. 迭代每个`DigitalSignature`集合中的对象。
3. 使用`IsValid`的财产`DigitalSignature`对象检查签名是否有效。

#### 问：我可以从 Word 文档中的数字签名中检索签名者的注释或签名原因吗？

答：是的，您可以从 Word 文档中的数字签名中检索签名者的注释或签名原因。这`Comments`的财产`DigitalSignature`对象提供对签名者在签名过程中指定的注释的访问。

#### 问：Aspose.Words for .NET 中的签名验证功能支持什么类型的文档？

答：Aspose.Words for .NET 中的签名验证功能支持对 DOCX 文件格式的 Word 文档中的数字签名进行验证。您可以使用此功能来验证 DOCX 文件中的签名。

#### 问：如何使用 Aspose.Words for .NET 访问 Word 文档中数字签名的证书详细信息？

答：要使用 Aspose.Words for .NET 访问 Word 文档中数字签名的证书详细信息，您可以访问`CertificateHolder`的财产`DigitalSignature`目的。来自`CertificateHolder`对象，您可以检索证书的各种详细信息，例如主题名称和颁发者名称。

#### 问：我可以使用 Aspose.Words for .NET 自定义 Word 文档中数字签名的显示或处理吗？

答：是的，您可以使用 Aspose.Words for .NET 自定义 Word 文档中数字签名的显示或处理。通过访问的属性和方法`DigitalSignature`对象，您可以提取所需的信息、执行其他验证或将签名验证过程集成到应用程序的工作流程中。

#### 问：是否可以使用 Aspose.Words for .NET 验证 Word 文档中的多个数字签名？

答：是的，可以使用 Aspose.Words for .NET 验证 Word 文档中的多个数字签名。通过迭代`DigitalSignatures`文档集合后，您可以单独访问和验证每个数字签名。

