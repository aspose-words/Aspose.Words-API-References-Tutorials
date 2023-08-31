---
title: 签署加密的 Word 文档
linktitle: 签署加密的 Word 文档
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 对加密的 Word 文档进行数字签名。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/signing-encrypted-document/
---
在本教程中，我们将指导您完成使用 Aspose.Words for .NET 签署加密 Word 文档功能的步骤。此功能允许您对使用解密密码加密的 Word 文档进行数字签名。请按照以下步骤操作：

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

## 结论

在本教程中，我们探索了使用 Aspose.Words for .NET 签署加密 Word 文档的过程。通过提供解密密码和签名证书，我们可以为加密文档添加数字签名。签署加密文档可确保其真实性和完整性，提供额外的安全层。 Aspose.Words for .NET 使您能够签署加密文档并维护 Word 文件的安全性和可信性。

### 常见问题解答

#### 问：Aspose.Words for .NET 中的文档签名是什么？

答：Aspose.Words for .NET 中的文档签名是指对 Word 文档进行数字签名的过程，以确保其真实性、完整性和不可否认性。它涉及使用证书向文档添加数字签名。

#### 问：什么是加密的Word文档？

答：加密的Word文档是使用密码加密的文档。加密是一种安全措施，通过对文档内容进行扰乱并使其在没有正确解密密码的情况下无法读取来保护文档内容。

#### 问：如何使用 Aspose.Words for .NET 签署加密的 Word 文档？

答：要使用 Aspose.Words for .NET 签署加密的 Word 文档，您需要提供解密密码以及签名证书。按着这些次序：
1. 在里面设置解密密码`SignOptions`目的。
2. 使用加载签名证书`CertificateHolder`班级。
3. 使用`DigitalSignatureUtil.Sign`方法对加密文档进行签名，并提供必要的参数。

#### 问：签署加密文档的目的是什么？

答：使用 Aspose.Words for .NET 对加密文档进行签名，即使文档已加密，您也可以向该文档添加数字签名。这提供了额外的安全层并确保加密内容的真实性和完整性。它允许收件人验证文档的来源并检测任何篡改。

#### 问：我可以在不提供解密密码的情况下签署加密文档吗？

答：不可以，要签署加密文档，您必须提供正确的解密密码。在应用数字签名之前，需要解密密码才能访问和修改文档的加密内容。

#### 问：我可以使用任何证书签署加密的 Word 文档吗？

答：要使用 Aspose.Words for .NET 签署加密的 Word 文档，您需要有效的 X.509 证书。证书可以从受信任的证书颁发机构 (CA) 获取，也可以使用自签名证书进行测试。

#### 问：我可以使用同一个证书签署多个加密的 Word 文档吗？

答：是的，您可以使用同一个证书签署多个加密的 Word 文档。使用以下命令加载证书后`CertificateHolder`类，您可以重用它来签署多个加密文档。

#### 问：我可以验证已签名的加密文档的数字签名吗？

答：是的，Aspose.Words for .NET 提供了验证已签名加密文档的数字签名的功能。您可以使用`DigitalSignatureUtil.Verify`验证数字签名的有效性和真实性的方法。

#### 问：Aspose.Words for .NET 支持什么文件格式来签署加密文档？

答：Aspose.Words for .NET 支持对 DOCX 文件格式的加密 Word 文档进行签名。您可以使用以下方法对加密的 DOCX 文件进行签名`DigitalSignatureUtil.Sign`方法以及必要的解密密码和证书。

#### 问：签署加密文档对加密有何影响？

答：使用 Aspose.Words for .NET 签署加密文档不会影响文档的加密。加密保持不变，并且数字签名被添加到加密内容中。数字签名提供了额外的安全性和验证，而不会影响应用于文档的加密。