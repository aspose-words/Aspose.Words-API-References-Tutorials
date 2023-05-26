---
title: 访问和验证签名
linktitle: 访问和验证签名
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 访问和验证 Word 文档中的数字签名。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/access-and-verify-signature/
---
在本教程中，我们将引导您完成使用 Aspose.Words for .NET 的访问和签名验证功能的步骤。此功能允许您访问 Word 文档中的数字签名并验证其有效性。请按照以下步骤操作：

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
	Console.WriteLine("*** Signature Found ***");
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
		Console.WriteLine("*** Signature Found ***");
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


