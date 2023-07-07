---
title: 签署现有签名行
linktitle: 签署现有签名行
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 对 Word 文档中的现有签名行进行签名。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/signing-existing-signature-line/
---

在本教程中，我们将引导您完成通过 Aspose.Words for .NET 使用现有签名行的签名功能的步骤。此功能允许您对 Word 文档中已有的签名行进行数字签名。请按照以下步骤操作：

## 第 1 步：加载文档并访问签名行

首先上传包含现有签名行的文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## 第2步：设置签名选项

创建 SignOptions 类的实例并设置签名选项，包括签名行 ID 和签名行图像：

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

请务必指定签名行图像的正确路径。

## 第三步：加载证书

首先使用 CertificateHolder 类加载签名证书：

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

请务必指定证书和关联密码的正确路径。

## 第 4 步：签署现有签名行

使用 DigitalSignatureUtil 类对现有签名行进行签名：

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

请务必指定源文档、签名文档和证书的正确路径。

### 使用 Aspose.Words for .NET 签署现有签名行的示例源代码

以下是使用 Aspose.Words for .NET 签署现有签名行的完整源代码：


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

通过执行以下步骤，您可以使用 Aspose.Words for .NET 轻松签署 Word 文档中的现有签名行。

