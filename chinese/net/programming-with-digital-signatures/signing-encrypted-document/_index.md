---
title: 签署加密文档
linktitle: 签署加密文档
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 对加密文档进行数字签名。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/signing-encrypted-document/
---

在本教程中，我们将指导您完成使用 Aspose.Words for .NET 签署加密文档功能的步骤。此功能允许您对使用解密密码加密的 Word 文档进行数字签名。请按照以下步骤操作：

## 第 1 步：设置签名选项

创建 SignOptions 类的实例并设置解密密码：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

请务必为加密文档指定正确的解密密码。

## 第2步：加载证书

首先使用 CertificateHolder 类加载签名证书：

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

请务必指定证书和关联密码的正确路径。

## 第 3 步：签署加密文档

使用 DigitalSignatureUtil 类对加密文档进行签名：

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

请务必指定加密文档、签名文档和证书的正确路径。

### 使用 Aspose.Words for .NET 签署加密文档的示例源代码

以下是使用 Aspose.Words for .NET 签署加密文档的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
通过执行以下步骤，您可以使用 Aspose.Words for .NET 轻松签署加密的 Word 文档。

