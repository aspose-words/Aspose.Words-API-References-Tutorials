---
title: 创建新签名行并设置提供商 ID
linktitle: 创建新签名行并设置提供商 ID
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建新的签名行并设置提供商 ID。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 创建新签名行和设置提供商 ID 功能的步骤。此功能允许您在 Word 文档中插入签名行、设置自定义选项并签署文档。请按照以下步骤操作：

## 第 1 步：创建文档和生成器

首先创建 Document 类的实例和 DocumentBuilder 对象：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：设置签名行选项

创建 SignatureLineOptions 类的实例并设置所需的选项：

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## 步骤 3：插入签名行

使用 DocumentBuilder 对象的 InsertSignatureLine() 方法将签名行插入到文档中：

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## 第 4 步：设置提供商 ID

使用 ProviderId 属性设置签名行的提供者 ID：

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

请务必为您的用例指定正确的提供商 ID。

## 第 5 步：保存文档

保存修改后的文档：

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

请务必指定正确的路径和文件名来保存文档。

## 第 6 步：签署文件

要签署文档，您需要设置签名选项并使用 DigitalSignatureUtil 类：

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

请务必指定文档、证书和签名文档的正确路径。

### 使用 Aspose.Words for .NET 创建新签名行并设置提供商 Id 的示例源代码

以下是创建新签名行并使用 Aspose.Words for .NET 设置提供程序 ID 的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

通过执行这些步骤，您可以使用 Aspose.Words for .NET 轻松创建新的签名行并在 Word 文档中设置提供商 ID。

