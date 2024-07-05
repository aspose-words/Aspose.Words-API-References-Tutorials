---
title: 签署 Word 文档
linktitle: 签署 Word 文档
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 对 Word 文档进行数字签名。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/sign-document/
---
在本教程中，我们将引导您完成使用 Aspose.Words for .NET 的文档签名功能的步骤。此功能允许您使用证书对 Word 文档进行数字签名。请按照以下步骤操作：

## 步骤 1：加载证书

首先使用 CertificationHolder 类加载签名证书：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

请确保指定证书和相关密码的正确路径。

## 第 2 步：签署文件

使用 DigitalSignatureUtil 类对文档进行签名：

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

确保为源文档和签名文档指定正确的路径。

### 使用 Aspose.Words for .NET 签署文档的示例源代码

以下是使用 Aspose.Words for .NET 签署文档的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

按照以下步骤，您可以轻松地使用 Aspose.Words for .NET 签署 Word 文档。

## 结论

在本教程中，我们探索了 Aspose.Words for .NET 中的文档签名功能。通过加载签名证书并使用`DigitalSignatureUtil.Sign`方法，我们可以对 Word 文档进行数字签名。文档签名提供身份验证并确保文档内容的完整性，使其成为安全可靠的文档管理的宝贵功能。

### 签署 word 文档常见问题解答

#### 问：Aspose.Words for .NET 中的文档签名是什么？

答：Aspose.Words for .NET 中的文档签名是指使用证书对 Word 文档进行数字签名的过程。此功能将数字签名添加到文档中，以确保文档内容的真实性、完整性和不可否认性。

#### 问：如何在 Aspose.Words for .NET 中加载签名证书？

答：要在 Aspose.Words for .NET 中加载签名证书，您可以使用`CertificateHolder`类。创建`CertificateHolder`通过提供证书文件的路径和相关密码。以下是示例：

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

确保提供证书的正确路径和相关密码。

#### 问：如何使用 Aspose.Words for .NET 签署 Word 文档？

答：要使用 Aspose.Words for .NET 签署 Word 文档，您可以使用`DigitalSignatureUtil`类。调用`Sign`方法，提供源文档的路径、签名文档（输出）的路径以及`CertificateHolder`对象。以下是示例：

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

确保为源文档和签名文档（输出）提供正确的路径。

#### 问：文件签署的目的是什么？

答：文档签名是一种确保文档真实性和完整性的方法。通过对文档进行数字签名，您可以提供其来源的证明，验证其内容未被更改，并建立不可否认性。文档签名通常用于法律、财务和敏感文档。

#### 问：我可以使用任何证书在 Aspose.Words for .NET 中进行文档签名吗？

答：要在 Aspose.Words for .NET 中进行文档签名，您需要使用有效的 X.509 证书。此证书可从受信任的证书颁发机构 (CA) 获取，也可以使用自签名证书进行测试。

#### 问：Aspose.Words for .NET 支持哪种文件格式的文档签名？

答：Aspose.Words for .NET 支持 DOCX 文件格式的 Word 文档签名。您可以使用`DigitalSignatureUtil`类别和相应的证书。

#### 问：我可以使用同一个证书签署多个 Word 文档吗？

答：是的，您可以使用同一份证书签署多个 Word 文档。使用`CertificateHolder`类，您可以通过调用`DigitalSignatureUtil.Sign`具有不同源和签名文档路径的方法。

#### 问：文件签名会修改原始文件吗？

答：使用 Aspose.Words for .NET 进行文档签名不会修改原始文档。相反，它会创建文档的数字签名副本，使原始文档保持完整。数字签名副本包含添加的数字签名，确保文档内容的完整性。

#### 问：我可以使用 Aspose.Words for .NET 验证签名文档的数字签名吗？

答：是的，Aspose.Words for .NET 提供了验证已签名文档的数字签名的功能。您可以使用`DigitalSignatureUtil.Verify`方法来检验数字签名的有效性和真实性。