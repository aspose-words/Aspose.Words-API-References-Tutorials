---
title: 签名加密的 Word 文档
linktitle: 签名加密的 Word 文档
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 对加密的 Word 文档进行数字签名。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/signing-encrypted-document/
---
在本教程中，我们将指导您完成使用 Aspose.Words for .NET 签名加密 Word 文档的功能的步骤。此功能允许您对使用解密密码加密的 Word 文档进行数字签名。请按照以下步骤操作：

## 步骤 1：设置签名选项

创建SignOptions类的实例，并设置解密密码：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

确保为加密文档指定正确的解密密码。

## 步骤2：加载证书

首先使用 CertificationHolder 类加载签名证书：

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

请确保指定证书和相关密码的正确路径。

## 步骤 3：对加密文档进行签名

使用 DigitalSignatureUtil 类对加密文档进行签名：

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

确保为加密文档、签名文档和证书指定正确的路径。

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
通过遵循这些步骤，您可以轻松地使用 Aspose.Words for .NET 签署加密的 Word 文档。

## 结论

在本教程中，我们探索了使用 Aspose.Words for .NET 签署加密 Word 文档的过程。通过提供解密密码和签名证书，我们可以向加密文档添加数字签名。签署加密文档可确保其真实性和完整性，从而提供额外的安全保障。Aspose.Words for .NET 使您能够签署加密文档并维护 Word 文件的安全性和可信度。

### 常见问题解答

#### 问：Aspose.Words for .NET 中的文档签名是什么？

答：Aspose.Words for .NET 中的文档签名是指对 Word 文档进行数字签名以确保其真实性、完整性和不可否认性的过程。它涉及使用证书向文档添加数字签名。

#### 问：什么是加密的 Word 文档？

答：加密的 Word 文档是使用密码加密的文档。加密是一种安全措施，它通过对文档内容进行打乱，使其在没有正确解密密码的情况下无法读取来保护文档内容。

#### 问：如何使用 Aspose.Words for .NET 签署加密的 Word 文档？

答：要使用 Aspose.Words for .NET 签署加密的 Word 文档，您需要提供解密密码以及签名证书。 请按照以下步骤操作：
1. 在中设置解密密码`SignOptions`目的。
2. 使用加载签名证书`CertificateHolder`班级。
3. 使用`DigitalSignatureUtil.Sign`方法对加密文档进行签名，并提供必要的参数。

#### 问：签署加密文件的目的是什么？

答：使用 Aspose.Words for .NET 对加密文档进行签名，即使文档已加密，您也可以向文档添加数字签名。这提供了额外的安全层，并确保了加密内容的真实性和完整性。它允许收件人验证文档的来源并检测任何篡改。

#### 问：我可以签署加密文档而不提供解密密码吗？

答：不可以，要签署加密文件，您必须提供正确的解密密码。在应用数字签名之前，需要解密密码才能访问和修改文档的加密内容。

#### 问：我可以使用任何证书签署加密的 Word 文档吗？

答：要使用 Aspose.Words for .NET 签署加密的 Word 文档，您需要有效的 X.509 证书。可以从受信任的证书颁发机构 (CA) 获取证书，也可以使用自签名证书进行测试。

#### 问：我可以使用同一个证书签署多个加密的 Word 文档吗？

答：是的，您可以使用同一份证书对多个加密的 Word 文档进行签名。使用`CertificateHolder`类，您可以重复使用它来签署多个加密文档。

#### 问：我可以验证已签名的加密文档的数字签名吗？

答：是的，Aspose.Words for .NET 提供了验证已签名加密文档数字签名的功能。您可以使用`DigitalSignatureUtil.Verify`方法来检验数字签名的有效性和真实性。

#### 问：Aspose.Words for .NET 支持哪种文件格式的加密文档签名？

答：Aspose.Words for .NET 支持对 DOCX 文件格式的加密 Word 文档进行签名。您可以使用`DigitalSignatureUtil.Sign`方法以及必要的解密密码和证书。

#### 问：签署加密文档会对加密产生什么影响？

答：使用 Aspose.Words for .NET 签署加密文档不会影响文档的加密。加密保持不变，数字签名会添加到加密内容中。数字签名提供额外的安全性和验证，而不会损害应用于文档的加密。